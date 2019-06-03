---
layout: post
title: Linux/Ubuntu系統目錄解析與Command指令全集
subtitle: 如何查找檔案？防火牆怎麼開？檔案權限怎麼設定？
tags: [tech, ubuntu, linux]
keywords : "ubuntu, linux, command, 指令, 查找檔案, 防火牆, 檔案權限" 
---

### 什麼是Linux?什麼是Ubuntu?
第一次接觸這兩個名詞的人一定會覺得疑惑，這到底是什麼呢(●Ω●;)<br>
其實簡單來說，就是[類Unix](https://zh.wikipedia.org/wiki/类Unix系统)的 **「作業系統」** <br>
更簡單的說，我們最常用的作業系統是[Windows](https://zh.wikipedia.org/wiki/Microsoft_Windows)或[macOS](https://zh.wikipedia.org/wiki/MacOS)<br>
而Linux跟Ubuntu就是可以運行電腦應用程式的作業系統環境喔！<br>
身為小小小RD的我，就來介紹一下這個作業系統的目錄及常用[Command](https://zh.wikipedia.org/wiki/命令提示字元)吧（人･ω･)<br>
本次介紹將分為：<br>
[系統檔案目錄](#系統檔案目錄) | [基本指令](#基本指令) | [使用者管理](#使用者管理) | [檔案控制](#檔案控制) | [檔案查找](#檔案查找) | [防火牆設定](#防火牆設定) | [網路設定](#網路設定)

### 系統檔案目錄

Linux作業系統應符合[FHS](https://zh.wikipedia.org/wiki/文件系统层次结构标准)檔案系統階層標準，每個資料夾也有相對應的目的與功能。<br>

| 目錄 | 說明 |
| :------ |:--- |
| / | 第一層根目錄。 |
| /root | 系統管理員的家目錄，僅有root權限可讀寫。 |
| /boot | 放置Linux系統啟動過程中需要的文件，例如：kernal、引導程序Grub等。 |
| /bin | binary，存放供所有用戶使用的完成基本維護任務的命令，例如：cat、ls、cp等。 |
| /sbin | 存放系統管理員可使用的文件，例如：mkdir、ifconfig、reboot等。 |
| /dev | device，存放系統設備文件，例如：硬碟驅動、鍵盤、滑鼠等。 |
| /etc | etcetera，存放系統主要配置文件及應用軟體設定檔。 |
| /home | 用戶的家目錄，儲存普通用戶個人文件，默認為/home/USERNAME。 |
| /lib | 存放系統函示庫及核心函式庫。 |
| /opt | optional，第三方軟體放置處，例如：Adobe Reader、google-earth等。 |
| /srv | service，網路服務啟動後所需數據存放處，例如：網站服務www。 |
| /tmp | temperary，暫存檔存放處。 |
| /usr | unix software resource，系統核心所在，包含所有共享文件。 |
| /var | 存放變數檔案，例如：系統log。 |

### 基本指令

* ls：list，列出當前資料夾檔案。

```shell
// -l 列出檔案詳細資料；-a 列出隱藏檔案
$ ls -la
// 列出指定類型檔案
$ ls *.pdf
```

* pwd：print work directory，列出當前資料夾路徑。

```shell
$ pwd
/Users/jasminmin/Blog
```

* cd：change directory，移動進入資料夾。

```shell
// 移動至當前資料夾底下con.f中
$ cd ./con.f
// 移動至上一層資料夾
$ cd ..
// 移動至上一次所在資料夾
$ cd -
```

* clear：清除terminal畫面。

```shell
$ clear
```

* reboot：重新開機。

```shell
$ reboot
```

* shutdown：關機。

```shell
// 系統立刻關機
$ shutdown -h now
// 系統十分鐘後關機
$ shutdown -h +10
```

### 使用者管理

* useradd USERNAME：新增使用者。

```shell
$ useradd alan
```

* passwd USERNAME：修改密碼，新使用者直接設定密碼；舊使用者須先輸入舊密碼。

```shell
$ passwd alan
```

* su USERNAME：切換使用者。

```shell
// 切換至使用者alan權限
$ su alan
// 切換回系統管理員權限
$ su root
```

* exit：若於一般使用者狀態，可離開當前權限。

```shell
$ exit
```

* who：查詢目前系統上的使用者。

```shell
$ who
```

* whoami：查詢當前使用者身份。

```shell
$ whoami
```

### 檔案控制

* mkdir DIRECTORY：make directory，建立資料夾。

```shell
// 在當前資料夾底下新增「blog」資料夾
$ mkdir blog
```

* touch FILENAME：建立檔案，可加入指定位置。

```shell
// 於「blog」資料夾中建立「post.md」檔案
$ touch blog/post.md
```

* cat FILENAME：顯示指定檔案內容。

```shell
$ cat blog/post.md
```

* vim FILENAME：修改指定檔案，進入編輯狀態後按「i」為插入模式，可開始編輯檔案；完成編輯按「esc」跳出插入模式，並輸入「:wq!」完成檔案儲存並離開。

```shell
$ vim blog/post.md
```

* mv：move files，移動檔案。

```shell
// mv PATH/FILENAME(原檔案位置) PATH/FILENAME(目的檔案位置)
$ mv blog/post.md temprary/post.md
```

* cp：copy，複製檔案。

```shell
// cp FILENAME /PATH(目的檔案位置)
$ cp post.md /temprary
```

* rm：remove file，刪除檔案或非空資料夾。

```shell
// rm FILENAME，刪除指定檔案
$ rm post.md

// rm -rf DIRECTORY，刪除指定資料夾
$ rm -rf blog
```

* file：檢查檔案類型。

```shell
// file FILENAME，檢查指定檔案
$ file README.md
README.md: HTML document text, UTF-8 Unicode text
```

* head/tail：檢查檔案前幾行/後幾行。

```shell
// head FILENAME，檢查檔案前幾行
$ head README.md

// tail FILENAME，檢查檔案後幾行
$ tail README.md
```

### 檔案查找

* find：查找檔案。<br>
-type [搜尋類型] 參數介紹<br>
`-type b`&nbsp;&nbsp;&nbsp;//block special file (特殊設備檔案)<br>
`-type c`&nbsp;&nbsp;&nbsp;//character special file (特殊設備檔案)<br>
`-type d`&nbsp;&nbsp;&nbsp;//directory (資料夾)<br>
`-type f`&nbsp;&nbsp;&nbsp;//regular file (一般檔案)<br>
`-type l`&nbsp;&nbsp;&nbsp;//symbolic link (連結檔)<br>
`-type p`&nbsp;&nbsp;&nbsp;//FIFO (命令管道)<br>
`-type s`&nbsp;&nbsp;&nbsp;//socket<br>

* 根據名稱搜尋檔案或資料夾<br>
`-name NAME`指定名稱；`-iname NAME`名稱不分大小寫

```shell
// 尋找家目錄底下指定資料夾或檔案
$ find ~ -name blog

// 尋找家目錄底下指定檔案
$ find ~ -name blog -type f

// 尋找當前目錄底下包含特定字串資料夾
$ find . -iname *blo* -type d
```

* 根據大小或時間搜尋檔案或資料夾<br>
`-size [ckMGTP]`指定大小；`-atime [time]`指定時間；`-amin [min]`指定分鐘

```shell
// 尋找當前目錄底下大於2Ｍ的檔案
$ fine . -size +2M -type f

// 尋找當前目錄底下超過2天沒被修改或存取的資料夾
$ fine . -atime +2 -type d

// 尋找當前目錄底下40分鐘內有修改或存取過的檔案
$ fine . -amin -40 -type f
```

* 根據檔案內容搜尋檔案<br>
 `-exec`後面的command為執行的指令；`grep -H`將符合的檔案路徑列出；<br>
 `{}`將被取代為檔案名稱路徑；`\`代表exec參數結束<br>

```shell
// 尋找家目錄底下的php檔，並且內容包含test字串
$ find ~ -name "*.php" -exec grep -H "test" {} \;
```

### 防火牆設定

* firewall-cmd：防火牆個是設定命令格式。

* 防火牆配置

```shell
// 安装防火牆
$ apt-get install firewalld firewall-config

// 啟動防火牆 
$ systemctl start  firewalld

// 查看防火牆狀態
$ systemctl status firewalld

// 停止防火牆
$ systemctl disable firewalld

// 禁用防火牆
$ systemctl stop firewalld
```

* 服務管理

```shell
// 查詢現有服務列表
$ firewall-cmd --list-services

// 開啟防火牆SSH服務
$ firewall-cmd --enable service=ssh

// 禁止防火牆SSH服務
$ firewall-cmd --disable service=ssh

// 新增http服務至內部
$ firewall-cmd --permanent --zone=internal --add-service=http
```

* 埠號管理

```shell
// 開啟防火牆TCP 443port
$ firewall-cmd --add-port=443/tcp

// 永久開啟防火牆UDP 8080port
$ firewall-cmd --permanent --add-port=8080/udp

// 重啟防火牆，當新增防火牆規則或埠號後重啟
$ firewall-cmd --reload
```

### 網路設定

* ifconfig：查詢系統網路卡狀況。

```shell
// 可以查詢IP、子遮罩網路及網路卡的硬體等資訊
$ ifconfig
```

* route：查看網路封包傳送路由狀況。

```shell
$ route
```

* netstat：查看網路連線狀況。

```shell
$ netstat
```

* nslookup：查詢或反查詢[Domain](https://jasminmin.com/2019-04-30-who-is-websites/)相對應IP。

```shell
// 查詢Google伺服器IP
$ nslookup www.google.com
Server:		192.168.1.1
Address:	192.168.1.1#53

Non-authoritative answer:
Name:	www.google.com
Address: 216.58.200.228
```

* ping IP/DNS：查看目的Domain是否有網路封包回應。

```shell
$ ping www.google.com
PING www.google.com (172.217.27.132): 56 data bytes
64 bytes from 172.217.27.132: icmp_seq=0 ttl=54 time=4.937 ms
64 bytes from 172.217.27.132: icmp_seq=1 ttl=54 time=5.354 ms
64 bytes from 172.217.27.132: icmp_seq=2 ttl=54 time=5.564 ms
64 bytes from 172.217.27.132: icmp_seq=3 ttl=54 time=6.128 ms
--- www.google.com ping statistics ---
4 packets transmitted, 4 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 4.937/5.599/6.251/0.364 ms
```


參考資料：[TechBridge 技術共筆部落格](https://blog.techbridge.cc/2017/12/23/linux-commnd-line-tutorial/)、[每日頭條](https://kknews.cc/other/bj9n9vm.html)、[camel's blog](https://blog.camel2243.com/2016/09/21/linux-find-指令，搜尋檔案資料夾名稱與全文搜尋/)、[Github/jaywcjlove](https://github.com/jaywcjlove/linux-command)

----------