---
layout: post
title: 如何查詢Domain?Whois網站推薦指南
subtitle: UR?IP?Domain?一起檢視連線網站的來源吧
tags: [tech, web]
keywords : "domain, 網頁安全, whois, 域名, 網站連線, URL" 
---

大家常說的「網址」，也就是URL，正是每個網站連線的位址 ʘ ͜ʖ ʘ<br>

### 什麼是URL?
>統一資源定位器，Uniform Resource Locator（URL），網際網路上標準的資源的位址。

簡而言之，就是網站連線的連結「link」<br>
像Jasmine部落格自我介紹的URL就是https://jasminmin.com/aboutme/<br>

### 什麼是IP?
>網際網路協定位址，Internet Protocol Address（IP），是分配給網路上使用網際協定的裝置的數字標籤。

每個網站都有自己的伺服器位址，也就是IP位址～<br>
當我們沒有對這些四組數字組成的IP做美化時，連線時的URL就是裸露的IP位址。<br>
如何將IP美化呢?就需要Domain的幫助囉！<br>

### 什麼是Domain?
>網域名稱，Domain Name（Domain），簡稱域名、網域，是由一串用點分隔的字元組成的網際網路上某一台電腦或電腦組的名稱，用於在資料傳輸時標識電腦的電子方位。

大家可以將Domain想成是IP的面具，舉例來說jasminmin.com就是我的部落格域名。<br>
如果把每個網站視為一間房子，而Domain就是他的門牌號碼囉！<br>
那URL跟Domain有什麼差別呢？<br>
我們將Domian視為URL的一部分，網站中的分頁就是需要靠URL做連結。<br>
接下來就進入正題吧(｡+･｀ω･´)<br>

科技爆炸的時代，大家什麼都喜歡[估狗](https://google.com)一下，然而你連線的網站安全嗎？<br>
是不是手機常跳出中獎畫面？是不是常常被廣告覆蓋呢？<br>
以下介紹「WHOIS」提供大家解決不明來源網站查詢吧～<br>

### 什麼是WHOIS?
>用來查詢網際網路中域名的IP以及所有者等資訊的傳輸協定。

早期的WHOIS查詢多以命令列介面（Command Line）存在，現在也有許多線上查詢工具，甚至可以一次向不同的資料庫查詢。<br>
我們只要將不明來源的網址或IP丟到網站進行查詢，就可以檢視該網站的來源！<br>
還有什麼狀況會需要查詢IP或Domain呢?<br>
* 查詢網域註冊商：通常購買域名採年份計，當你忘記從哪家註冊商購買時可藉此查詢。
* 查詢註冊時間及到期日：域名逾期將造成網站無法連線，記得查看到期日喔！
* 檢查域名是否遭註冊：當你想創建自己的網站域名，可先至WHOIS查詢。
* 網站IP及地理位置：當你的電腦或應用程式連線至不明IP或Domian，可以查看所屬公司或地理位置。

除了上述這些，我們也可以當作連線保護的機制<br>
查詢網域可以確認是否為「高風險國家」所註冊之網域，避免遭個資釣魚！<br>

------------
### [WHOis.net](https://www.whois.net)
![whois.net](/img/1080430/1.png)

WHOis.net主要為查詢該DNS是否已被註冊，並顯示註冊商公司、註冊郵件、電話、地址及有效到期日等資訊。

------------
### [Whois](https://www.whois.com/whois/)
![Whois](/img/1080430/2.png)

Whois網站提供該DNS註冊商公司、郵件、電話、地址及有效到期日等資訊，並提供該網域由哪間域名公司售出，網站旁邊也會提供類似網域及建議售價。

------------
### [who.is](https://who.is)
![who.is](/img/1080430/3.png)

who.is網站提供該DNS註冊商公司、郵件、電話、地址及有效到期日等資訊，也提供可申請的類似網域名稱。

------------
### [GoDaddy](https://tw.godaddy.com/whois)
![godaddy](/img/1080430/4.png)

Godaddy本身即是可供購買網域的服務商，其中也有讓使用者查詢DNS的服務，但在查詢過程中會驗證使用者是否是機器人，相較前三項小麻煩一點。

------------
### [IpLocation](https://www.iplocation.net)
![iplocation](/img/1080430/5.png)

IpLocation針對該DNS做IP查詢，查詢結果顯示[IP2LOCATION](https://www.ip2location.com)、[ipinfo](https://ipinfo.io)、[dbip](https://www.db-ip.com)三網站的結果，使用者可相互比對做地理位置確認。

------------
### [Neustar](https://www.ultratools.com/tools/ipWhoisLookupResult)
![neustar](/img/1080430/6.png)

neustar是一個提供多種服務的網站，包括IPv6、Email等皆可在網站內搜尋，輸入DNS時記得去除`https://`，否則會一直顯示該網址無效喔！<br>
而neustar可查詢到的資訊除註冊商或註冊人的詳細資料外，包括主機所在IP、國家、城市皆會提供，這時候就可以做目的性多重驗證。

------------
上述介紹網站中，前四項為WHOIS查詢瀏覽器，主要針對該域名註冊廠商及時間做查詢。<br>
後兩項皆可使用IP及Domian做查詢，內容主要針對伺服器位置做地圖標示。<br>
如果有任何推薦的查詢網站，也歡迎大家留言告訴大家喔╭( ･ㅂ･)و

參考資料：[維基百科](https://zh.wikipedia.org/wiki)、[免費資源網路社群](https://free.com.tw/who-is/)

----------