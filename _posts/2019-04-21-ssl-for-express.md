---
layout: post
title: 如何在Node.js Express框架上設定Let's Encrypt憑證？
subtitle: 讓你的Domain出現HTTPS小鎖頭安全連線吧！
tags: [tech, node.js, SSL]
---

什麼是Express框架(ↂ_ↂ？<br>
>Express 是目前最穩定、使用最廣泛開發框架，並且是[Node.js官方](https://nodejs.org/en/)唯一推薦的Web開發框架。

那什麼是Let's Encrypt憑證呢？<br>
>[Let's Encrypt](https://letsencrypt.org)是一個於2015年三季度推出的數位憑證認證機構，旨在以自動化流程消除手動建立和安裝憑證的複雜流程，並推廣使全球資訊網伺服器的加密連接無所不在，為安全網站提供免費的SSL/TLS憑證。

大家在利用Nginx+Express架站時，大家都如何設定SSL憑證呢？<br>
Let's setup **Let's Encrypt** for our Express Sites!<br>
以下將利用Cerbot憑證管理工具協助Express申請SSL憑證，步驟簡述：<br>
1. 安裝Certbot憑證管理工具
2. 藉由Certbot申請SSL憑證
3. Nginx伺服器設定檔編輯
4. 防火牆設定

## 安裝Certbot憑證管理工具
如果是在 Red Hat/Fedora/CentOS 作業系統下指令使用**yum**，在 Debian/ubuntu 作業系統使用**apt-get**：<br>
```shell
sudo yum install certbot
```
如果使用macOS需要使用certbot憑證管理工具，也可以輸入安裝：<br>
```shell
brew install certbot
```
## 藉由Certbot申請SSL憑證
在申請憑證之前，大家記得先[申請免費域名](https://www.noip.com/)或直接[購買域名](https://www.namecheap.com)<br>
下指令時請使用root全線進行申請：<br>
```shell
sudo certbot certonly --manual
```
接下來會詢問你的email：<br>
```shell
Saving debug log to /var/log/letsencrypt/letsencrypt.log Plugins
selected: Authenticator manual, Installer None Enter email address 
(used for urgent renewal and security notices) (Enter 'c' to 
cancel):test@gmail.com 
```
詢問是否接受服務條款：<br>
```shell
Please read the Terms of Service at
https://letsencrypt.org/documents/LE-SA-v1.2-November-15-2017.pdf. 
You must agree in order to register with the ACME server at
https://acme-v02.api.letsencrypt.org/directory
(A)gree/(C)ancel: A
```
詢問是否分享郵箱給Electronic Fronitier基金會（這是開發Certbot的組織），作為分享近期組織活動的宣傳管道：
```
Would you be willing to share your email address with the Electronic Frontier
Foundation, a founding partner of the Let's Encrypt project and the non-profit
organization that develops Certbot? We'd like to send you email about our work
encrypting the web, EFF news, campaigns, and ways to support digital freedom.
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
(Y)es/(N)o: Y
```
接下來輸入你所想要申請的域名：<br>
```shell
Please enter in your domain name(s) (comma and/or space separated)  (Enter 'c'
to cancel): jasminmin.com
```
詢問IP是否可被記錄：<br>
```
Obtaining a new certificate
Performing the following challenges:
http-01 challenge for copesflavio.com

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
NOTE: The IP of this machine will be publicly logged as having requested this
certificate. If you're running certbot in manual mode on a machine that is not
your server, please ensure you're okay with that.

Are you OK with your IP being logged?
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
(Y)es/(N)o: y
```
依下列提示在web伺服器位置中建立「.well-known/acme-challenge」兩層資料夾並建立檔案與編輯檔案內容：<br>
```shell
Create a file containing just this data:

TS_oZ2-ji23jrio3*****3iroj_U51u1o0x7rrDY2E.*****_voCOsrpddP_2kpodd2opeko2pke-UAPk21sW1c

And make it available on your web server at this URL:

http://jasminmin.com/.well-known/acme-challenge/TS_oZ2-ji23jrio3j2irj3iroj_U51u1o0x7rrDY9A
```
完成檔案建立後可輸入網址檢視是否可被連結下載Ψ(｀▽´)Ψ<br>
確認完畢按下`Enter`等待數秒憑證就建立完成囉！<br>
大家要把憑證key放置的位置記錄下來，待會Nginx伺服器設定終將使用到：<br>
```
Waiting for verification...
Resetting dropped connection: acme-v02.api.letsencrypt.org
Cleaning up challenges
Resetting dropped connection: acme-v02.api.letsencrypt.org

IMPORTANT NOTES:
 - Congratulations! Your certificate and chain have been saved at:
   /etc/letsencrypt/live/jasminmin.com/fullchain.pem
   Your key file has been saved at:
   /etc/letsencrypt/live/jasminmin.com/privkey.pem
   Your cert will expire on 2019-10-31. To obtain a new or tweaked
   version of this certificate in the future, simply run certbot
   again. To non-interactively renew *all* of your certificates, run
   "certbot renew"
 - If you like Certbot, please consider supporting our work by:

   Donating to ISRG / Let's Encrypt:   https://letsencrypt.org/donate
   Donating to EFF:                    https://eff.org/donate-le
```
## Nginx伺服器設定檔編輯
接下來設定Nginx伺服器中的設定檔，先安裝certbot-nginx套件：
```shell
sudo yum install certbot-nginx
```
完成後修改nginx.conf檔中`server name`為自己的域名：
```shell
sudo vi /etc/nginx/nginx.conf
```
```shell
server{
    listen       80 default_server;
    listen       [::]:80 default_server;
    server_name  jasminmin.com;
    ......
}
```
在Nginx伺服器中conf.d資料夾裡建立自訂名稱conf設定檔，conf.d資料夾為Nginx為開發者自定義設定檔放置位置：<br>
```shell
sudo touch /etc/nginx/conf.d/setting.conf
vim /etc/nginx/conf.d/setting.conf
```
檔案中輸入設定：<br>
```shell
server {
  # 傾聽 HTTPS 標準埠號 443
  listen 443 ssl http2;

  # 同時啟用 IPv6 的 HTTPS 安全加密網頁
  listen [::]:443;

  server_name sendtest.kerorotw.com;

  index index.php index.html index.htm;

location /api/ws {
	proxy_redirect off;
	proxy_pass http://0.0.0.0:1443;
	proxy_http_version 1.1;
	proxy_set_header Upgrade $http_upgrade;
	proxy_set_header Connection "upgrade";
	proxy_set_header Host $http_host;
}


location / {
	proxy_pass	http://0.0.0.0:1443;
	proxy_set_header	Host	$host;
	proxy_set_header	X-Real-IP	$remote_addr;
	proxy_set_header	X-Forwarded-For	$proxy_add_x_forwarded_for;
}
	access_log off;

# 設定 SSL 憑證
	ssl_certificate /etc/letsencrypt/live/sendtest.kerorotw.com/fullchain.pem;
	ssl_certificate_key /etc/letsencrypt/live/sendtest.kerorotw.com/privkey.pem;

	ssl on;
	ssl_session_timeout 5m;
	ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
	ssl_prefer_server_ciphers on;
	ssl_ciphers "EECDH+CHACHA20:EECDH+CHACHA20-draft:EECDH+AES128:RSA+AES128:EECDH+AES256:RSA+AES256:EECDH+3DES:RSA+3DES:!MD5";
	ssl_session_cache builtin:1000 shared:SSL:10m;
  
}
```
完成設定檔編輯後記得將Nginx伺服器重啟，不然以上就是白費工囉：
```shell
sudo nginx -s reload
```
## 防火牆設定
接下來進行防火牆設定，分別對udp及tcp都開啟443埠號：<br>
```shell
firewall -cmd --parmanent --add-port=443/udp
firewall -cmd --parmanent --add-port=443/tcp
```
設定完成會出現`success`，接下來重啟防火牆：<br>
```shell
firewall -cmd --reload
```
這個時候可以嘗試在Domain前面加上https，如果連線成功就代表完成啦☆*ヾ(-∀・*)*+☆<br>

---------