---
layout: post
title: MacOS運用terminal進行遠端連線及檔案傳輸
subtitle: 使用ssh,sftp,scp快速Tips!
tags: [lifetime, mac, linux]
keywords : "MacOS, 遠端連線, ssh, sftp, scp, 遠端檔案傳輸" 
---

時隔三個月擠出微微時間d( ･ω´･+)<br>
分享一下MacOS上遠端傳檔及連線的小撇步給大家！<br>
當需要從MacOS上連線VPS或Linux作業系統時都用什麼方法呢？<br>
你知道可以不透過其他application進行連線嗎？<br>
試看看不安裝任何程式就可以連線吧<br>
with ~~STRONG~~ Command Line(つ ͡° ͜ʖ ͡°)つ<br>

---

### Use of SSH

* 連線遠端主機，連線後輸入密碼
```shell
# ssh hostName@IP
ssh root@192.168.0.1
```

* 針對特定port連線
```shell
# ssh -p portNum hostName@IP
ssh -p 22 root@192.168.0.1
```

### Use of SCP

* 遠端複製至本機
```shell
# scp -r hostName@IP:remotePath localPath
scp -r root@192.168.0.100:/home/test.zip /Users/jasmine/downloads/
```

* 本機複製至遠端
```shell
# scp -r localPath/fileName hostName@IP:remotePath
scp -r /Users/jasmine/downloads/test.pdf root@192.168.0.100:/home/
```

### Use of SFTP

* 連線遠端主機，連線後輸入密碼
```shell
# sftp hostName@IP:remotePath
sftp root@192.168.100.1
```

* 上傳檔案或資料夾
```shell
# 查看遠端連線後當前資料夾
sftp> pwd
Remote working directory: /home/root/remote/
# 查看本機端當前資料夾
sftp> lpwd
Local working directory: /Users/jasmine/local/
# 上傳檔案 put -r localPath/fileName remotePath
put -r /Users/jasmine/local/file.pdf  /home/root/remote/
# 上傳資料夾 put -r localPath/folderName/* remotePath
put -r /Users/jasmine/local/testFolder/* /home/root/remote/newFolder/
```

* 下載檔案或資料夾
```shell
# 下載檔案 get -r remotePath/fileName localPath
put -r /home/root/remote/file.pdf  /Users/jasmine/local/
# 下載資料夾 put -r remotePath/folderName/* localPath
put -r /home/root/remote/testFolder/* /Users/jasmine/local/newFolder/
```

### How to exit?

要怎麼離開遠端主機呢?<br>
其實就是`exit`喔！<br>
```shell
exit
```

---
That's all.(ง •̀ω•́)ง✧<br>
Let's call it a day~