---
layout: post
title: 如何在Windows、Mac或Linux上快速建立指定大小檔案?
subtitle: 各式作業系統中一行指令搞定空白檔案建立
tags: [tech, Windows, Mac, Ubuntu]
keywords : "windows, mac, ubuntu, 空白檔案, 指定大小, 檔案建立, fallocate, mkfile, fsutil" 
---

工具測試時需要各式大小的檔案，熊熊ʕ◉ᴥ◉ʔ找不到嗎？<br>
對！我就是那個不想隨便拿一個檔案測試的傢伙<br>
那就看看在[Windows](#Windows)、[Mac](#Mac)或[Ubuntu](#Ubuntu)上如何建立指定大小的空白檔案吧～<br>

##  <font color="#6495ED">Windows</font>

### Step1 開啟CMD

快速開啟命令提示字元，輸入`Windows鍵`及`cmd`並按下`Enter`<br>

![w-1](/img/1080603/w-1.png)

### Step2 前往檔案產生位置

輸入`cd <directory>`，前往欲產生檔案的位置，以下路徑前往桌面<br>

![w-2](/img/1080603/w-2.png)

### Step3 建立檔案

輸入`fsutil`指令建立指定大小檔案，其中檔案大小單位為**kilo-byte**<br>
1KB：1 X 1024 = 1024<br>
1MB：1 X 1024 X 1024 = 1048576<br>
1GB：1 X 1024 X 1024 X 1024 ＝ 1073741824<br>
```shell
fsutile file createnew <file_name> <file_size_in_kBs>
```
以下範例為「在桌面建立名為**TEST**的1GB大小檔案」<br>

![w-3](/img/1080603/w-3.png)

##  <font color="#6495ED">Mac</font>

### Step1 開啟CMD

Mac開啟CMD後預設位置在Home底下，可自行更改檔案位置<br>

![m-1](/img/1080603/m-1.png)

### Step2 建立檔案

輸入`mkfile`指令建立指定大小檔案<br>
```shell
mkfile [-n] size[b|k|m|g] filename
```
可直接輸入檔案大小，[b|k|m|g]代表Byte、KB、MB、GB<br>
以下範例為「在Home目錄底下建立名為**Mac_Test**的1KB大小檔案」<br>

![m-2](/img/1080603/m-2.png)

##  <font color="#6495ED">Ubuntu</font>

### Step1 開啟CMD

這個範例的作業系統是以遠端連線進入，大家在本機可以直接開啟CMD<br>
完成連線後輸入`cd home`進入home目錄底下<br>

![u-1](/img/1080603/u-1.png)

### Step2 建立檔案

輸入`fallocate`指令建立指定大小檔案<br>
```shell
fallocate -l <file_size> <file_name>
```
以下範例為「在Home目錄底下建立名為**Ubuntu_Test**的4GB大小檔案」<br>

![u-2](/img/1080603/u-2.png)

----------

以上，大家可以在各作業系統底下建立指定大小檔案啦 ༼ つ◕(oo)◕༽つ<br>
