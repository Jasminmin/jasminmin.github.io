---
layout: post
title: 思科CCNA協定辭海
subtitle: ARP?ICMP?TTL?快速查找協定名稱與名詞解釋
tags: [tech, CCNA]
keywords : "CCNA, 思科, 名詞解釋, 協定解釋" 
---

爵士米最近上了CCNA的課程，發現第一步最重要的是把「名詞解釋」搞清楚！<br>
所以依照網路模型做分類，針對各層中的協定與名詞作基本解釋<br>
這時候大家要快速查找名詞定義就方便多囉٩(●˙▿˙●)۶…⋆ฺ<br>

### 鏈結層協定與名詞解釋

* Ethernet：乙太網路，IEEE組織的IEEE 802.3標準制定了乙太網路的技術標準，規定包括實體層的連線、電子訊號和媒介存取層協定的內容。

* PPP：點對點協定(Point-to-Point Protocol)，用於兩節點間建立直接的連接，並可以提供連接認證、傳輸加密（使用ECP，RFC 1968）以及壓縮。

* HDLC：高級數據鏈路控制(High-Level Data Link Control)，Cisco設備預設所使用的封裝協定，該協定不依賴於任何一種字元編碼集，「0比特插入法」易於硬體實現，全雙工通信方式，有較高的數據鏈路傳輸效率。

* Frame Relay：訊框中繼，一種有效的資料傳輸技術，它可以在一對一或者一對多的應用中快速而低廉的傳輸數位資訊。

* MAC Address：媒體存取控制位址(Media Access Control Address)，也稱為區域網路位址（LAN Address），乙太網路位址（Ethernet Address）或實體位址（Physical Address），它是一個用來確認網路裝置位置的位址。

* CSMA/CD：載波偵測多重存取/碰撞偵測(Carrier Sense Multiple Access with Collision Detection)，當節點要發送訊號時，會先偵測通道是否有其他節點正在使用，當通道沒有被其他節點使用時立即傳送封包，封包傳送後檢查是否發生碰撞，若發生碰撞則對通道發出高頻訊號高知其他節點已經發生碰撞，碰撞後隨機等待一段時間重新發送封包。

* MPLS：多協定標簽交換(Multi-Protocol Label Switching)，一種在開放的網際網路上利用標籤啟動資料高速、高效傳輸的新技術，多協定的意涵是指MPLS不但可以支援多種網路層層面上的協定，還可以相容第二層的多種資料鏈路層技術。

* STP：擴展樹協定(Spanning Tree Protocol)，該協定可封鎖某些埠，只讓任何一對LAN的區段之間(Collision domain)存在一條有效路徑。

* NIC：網路介面卡(Network Interface Card)，用來允許電腦在電腦網路上進行通訊的電腦硬體。

### 網際網路層協定與名詞解釋

* IP：網際網路協定(Internet Protocaol)，根據來源主機與目的主機的位址傳送封包進行資料交換。

* IP定址：識別網路中的每個設備。

* IP路由：提供設備之間轉送IP封包的服務。

* ARP：位址解析協定(Address Resolution Protocol)，透過解析網路層位址(IP)來找尋資料鏈結層位址(MAC)的網路傳輸協定。

* ICMP：網際網路控制訊息協定(Internet Control Message Protocol)，解析網路封包或是分析路由的情況，於網際網路協定(IP)中傳送控制訊息。

* NAT：網路位址轉換(Network Address Translation)，在IP封包通過路由器或防火牆時重寫來源IP地址或目的IP位址的技術。

* RIP：路由訊息協定(Routing Information Protocol)，以路由跳數作為計數單位的路由協議，適用於比較小型的網絡環境。

* OSPF：開放式最短路徑優先(Open Shortest Path First)，隸屬內部網路關協定(IGP)，運作於自治系統內部，採用的最短路徑優先演算法，沒有設備數量(Hop Count)的限制。

* EIGRP：加強型閘道間選徑協定(Enhanced Interior Gateway Routing Protocol)，由Cisco所開發的，網路路徑收斂速度相當快，而所佔用的網路頻寬也相當小，在最短時間裡面，以最少的成本計算出最佳網路傳送路徑。

### 傳輸層協定與名詞解釋

* TCP：傳輸控制協定(Transmission Control Protocol)，一種連接導向的、可靠的、基於位元組流的傳輸層通訊協定，包含連接建立(connection establishment)、資料傳送(data transfer)和連接終止(connection termination)三階段。

* UDP：使用者資料流協定(User Datagram Protocol)，只提供資料的不可靠傳遞，一旦把應用程式發給網路層的資料傳送出去，就不保留資料備份，沒有連線要求、連線終止、以及流量控制的管理程序。

### 應用層協定與名詞解釋

* HTTP：超文本傳輸協定(HyperText Transfer Protocol)，一個用戶端和伺服器端之間請求和應答的標準，通常使用TCP協定，透過使用網頁瀏覽器、網路爬蟲或者其它的工具，用戶端發起一個HTTP請求到伺服器上指定埠(預設埠為80)。

* FTP：檔案傳輸協定(File Transfer Protocol)，一個用於在電腦網路上在用戶端和伺服器之間進行檔案傳輸的應用層協定。

* SMTP：簡單郵件傳輸協定(Simple Mail Transfer Protocol)，基於文字在網際網路上傳送電子郵件的標準。

* SNMP：簡單網路管理協定(Simple Network Management Protocol)，支援網路管理系統，用以監測連接到網路上的裝置是否有任何引起管理上關注的情況。

* DNS：網域名稱系統(Domain Name System)，作為將域名和IP位址相互對映的一個分散式資料庫，能夠使人更方便地存取網際網路。

* POP3：郵局協定(Post Office Protocol)，用於支援使用用戶端遠端管理在伺服器上的電子郵件。

| Port | Protocol | Application |
| :------ |:--- | :--- |
| 20 | TCP | FTP Data |
| 21 | TCP | FTP Control |
| 22 | TCP | SSH |
| 23 | TCP | Telnet |
| 25 | TCP | SMTP |
| 53 | TCP,UDP | DNS |
| 67 | UDP | DHCP Server |
| 68 | UDP | DHCP Client |
| 69 | TCP | TFTP |
| 80 | TCP | HTTP |
| 110 | TCP | POP3 |
| 161 | TCP | SNMP |
| 443 | TCP | SSL |
| 514 | TCP | Syslog |

▲ 常見應用層協定及其埠號

### 其他名詞解釋

* IOS：Cisco設備作業系統(Internetwork Operat)，控制交換器所有可執行的功能。

* OSI模型：開放式系統互連通訊參考模型(Open System Interconnection Reference Model)，一種概念模型，由國際標準化組織提出，一個試圖使各種電腦在世界範圍內互連為網路的標準框架，定義於ISO/IEC 7498-1。

* IPS模型：網際網路協議(Internet Protocol Suite)，是一個網路通訊模型，以及一整個網路傳輸協定家族，為網際網路的基礎通訊架構，被通稱為TCP/IP協定套組。

![OSI](/img/1080531/OSI.png){:width="80%"}<br>
▲ OSI與TCP/IP綜合比較圖

* Telnet：使用於network及LAN中，以虛擬終端機形式提供雙向的文字Command。

* CPE：客戶端設備(Customer Premises Equipment)。

* CSU/DSU：通道服務單元/資料服務單元(Channel Service Unit/Data Service Unit)，是用戶端(User End)與電信局局端(Central Office)間E1/T1線路傳輸的數位式數據機，也是WAN與LAN間的基礎介質，具有傳輸語音、數據和影像的功能，CSU/DSU通常合併放在一個硬體中連結在一起使用。

* ISP：網際網路服務供應商(Internet service Provider)。

* TTL：存活時間(Time To Life)，一個封包在經過一個路由器時，可傳遞的最長距離(躍點數)。

* CLI：命令列介面(Command-Line Interface)，在圖形使用者介面得到普及之前使用最為廣泛的使用者介面，它通常不支援滑鼠，用戶通過鍵盤輸入指令。

* VTY：虛擬終端機(Virtual Teletype Terminal)。

* AAA：認證授權與計費(Authentication, Authorization, Accouting)，泛指伺服器與網路設備上對使用者的控制與監察，以達到企業或組織的安全準則。

* RADIUS：遠端用戶撥入驗證服務(Remote Authentication Dial In User Service)，一個AAA協定，意思就是同時兼顧驗證、授權及計帳三種服務的一種網路傳輸協定，通常用於網路存取、或流動IP服務，適用於局域網及漫遊服務。

* TACACS：終端訪問控制器訪問控制系統(Terminal Access Controller Access-Control System)，用於認證的計算機協議，在UNIX網絡中與認證伺服器進行通信，TACACS允許遠程訪問伺服器與認證伺服器通信，以決定用戶是否有權限訪問網絡。

* TACACS+：終端訪問控制器訪問控制系統(Terminal Access Controller Access-Control System Plus)，為路由器、網絡訪問伺服器和其他互聯計算設備通過一個或多個集中的伺服器提供訪問控制的協議，TACACS+提供了獨立的認證、授權和記帳服務。

* AP：無線網路基地台(Wireless Access Point)，是電腦網路中一種連接無線網路至有線網路(乙太網)的裝置。

* VTP：虛擬區域網路幹道協定(VLAN Trunking Protocol)，為Cisco專屬協定，讓Cisco交換器可交換VLAN組態資訊，當一個VLAN被新增、刪除或修改時，VTP會讓所有交換器進行同步動作，然而因具有高度隱憂，現許多企業已不再採用。

* IGP：內部通訊協定(Interior Gateway Protocols)，在同一個自治系統(Autonomous System)內部運行的路由通訊協定，例如：OSPF、EIGRP、RIP。

* EGP：外部通訊協定(Exterior Gateway Protocols)，在不同自治系統之間運行的路由通訊協定，例如：BGPv4。

* Autonomous System：自治系統，在同一管理架構下的所有網路。

----------

參考資料：[維基百科](https://zh.wikipedia.org/wiki)、[ICND1/ICND2](https://www.books.com.tw/products/0010757652)