---
layout: post
title: 如何遠端連線到VPS上的主機>>>Remote Desktop!
subtitle: Windows及macOS遠端連線Windows on VPS~
tags: [tech, windows, mac]
keywords : "remote desktop, windows, mac, 遠端連線, VPS" 
---

大家常用VPS架站或Run程式測試嗎？<br>
如果不熟悉指令或需要圖形化介面時該怎麼辦呢(◎_◎;)<br>
今天來教大家如何在Windows及Mac上進行遠端桌面連線吧！<br>
以下會依[Windows](#windows)、[Mac](#mac)兩個作業系統做步驟講解<br>

---

首先要在VPS服務商架設一台符合作業系統需求的伺服器主機<br>
對於服務商大家都各有所好，爵士米是使用大名鼎鼎的[Vultr](https://www.vultr.com)<br>
為了讓大家增加親切感我們選擇Windows作業系統的虛擬主機<br>
在Vultr架設Windows作業系統每個月需要基本16美金<br>
額外則是視你所需要的Server Size決定價格<br>
這邊我們僅選擇最低55GB SSD及2G記憶體的規格<br>

![vultr-1](/img/1080801/vultr-1.png)

待數分鐘主機建立完成後，就可以查看所建立伺服器IP囉<br>

![vultr-２](/img/1080801/vultr-2.png)

##  <font color="#6495ED">Windows</font>

### Step1 遠端桌面連線程式

Windows主機中可鍵入`Windows+R`搜尋***mstsc***開啟遠端桌面程式<br>
開啟後輸入所要連線的主機IP或DNS及使用者名稱，並點擊「連線」<br>

![win-1](/img/1080801/win-1.png){:width="60%"}

### Step2 信任遠端連線

跳出信任警訊時點擊「連線」以信任該伺服器<br>

![win-2](/img/1080801/win-2.png){:width="60%"}

### Step3 初始化遠端連線

![win-3](/img/1080801/win-3.png){:width="60%"}

### Step4 身份驗證

完成初始化後將跳出Windows安全性警示，輸入VPS上Username及Password進行連線<br>

![win-4](/img/1080801/win-4.png){:width="60%"}

### Step5 跳過警訊

顯示警訊時請跳過，但如果不是個人VPS請不要亂跳過喔<br>

![win-5](/img/1080801/win-5.png){:width="60%"}

### Step6 完成遠端連線

待遠端連線開機後就可以連線到我們自己架的VPS囉！<br>
這時候的使用方式就跟一般電腦一樣～<br>

![win-6](/img/1080801/win-6.png)

---

##  <font color="#6495ED">Mac</font>

### Step1 下載「Microsoft Remote Desktop 10」

Mac進行遠端桌面連線需要借助App的力量啦～<br>
大家可以到App Store下載「Microsoft Remote Desktop 10」<br>

![mac-1](/img/1080801/mac-1.png)

### Step2 Add Desktop

下載完成後開啟App，並點擊「Add Desktop」<br>

![mac-2](/img/1080801/mac-2.png){:width="80%"}

### Step3 輸入連線資訊

於PC Name欄位填入VPS的IP或DNS並且取一個自己認得的主機名稱<br>

![mac-3](/img/1080801/mac-3.png){:width="80%"}

### Step4 開啟Desktops

雙擊剛才所建立的桌面<br>

![mac-4](/img/1080801/mac-4.png){:width="80%"}

### Step5 身份驗證

輸入VPS上Username及Password進行連線<br>

![mac-5](/img/1080801/mac-5.png){:width="80%"}

### Step6 完成遠端連線

![mac-6](/img/1080801/mac-6.png)

---

以上，就可以輕鬆的進行VPS遠端桌面連線啦・+(*゜∀゜*)+・<br>