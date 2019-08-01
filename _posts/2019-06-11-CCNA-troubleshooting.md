---
layout: post
title: 思科CCNA故障排除解析
subtitle: 乙太網路介面shutdown怎麼辦？Default Router的IP設定錯誤？
tags: [tech, CCNA]
keywords : "CCNA, 思科, 故障排除, shutdown" 
---

你把CCNA裡面會出現的[專有名詞](https://jasminmin.com/2019-05-31-CCNA-words/)都搞懂了嗎？<br>
進入課本書海是不是覺得有點混亂？<br>
其實在每個章節最後綜整都會有故障排除方式（๑✧∀✧๑）<br>
以下整理了各主題式故障排除方法，讓大家更快速記憶指令<br>

## 乙太網路故障排除

### 介面狀態檢查指令

```shell
# 詳列式
＃ show interfaces
# 表列式
＃ show interfasces description
# 表列式
＃ show interfaces status
```

### 介面無法運作的狀態及原因

| Interface Status | Line Protocol Status | Status | Results |
| :------ |:--- | :--- | :--- |
| Administratively Down | Down | 停用 | 介面以shutdown命令設定 |
| Down | Down | 無連線(Layer 1發生問題) | 沒有接上網路線、網路線損壞、網路線腳味出錯、另一端設備關機、另一個介面關閉或錯誤停用 |
| Up | Down | 無連線(Layer 2發生問題) | 不會出現在區域網路交換器上 |
| Down | Down(err-disabled) | 錯誤停用 | 該介面被埠安全防護停用，針對介面下shutdown及no shutdown指令 |
| Up | Up | 連線 | 介面運作中 |

### 介面速率與雙工模式問題

1. 速率未知，介面將使用10Mbps，採半雙工
2. 透過檢查線路上的訊號，感應到對接設備的速率
 * 速率10或100Mbps，預設使用半雙工
 * 速率1000Mbps，預設使用全雙工

### 分析訊框轉送至何處

```shell
＃ show mac address-table
```

* 交換器本身需要用到的MAC
* 埠安全防護功能的設定
* 動態學習的MAC位址

----------------

## IPv4故障排除

### 選擇符合需求的遮罩

* 子網路與主機位元最低數量選擇
 * 判斷網路位元數量
 * 確定子網路最小值
 * 確定主機數最小值
* 遮罩需求確認
 * 無遮罩符合需求：172.16.0.0/16，300個子網路，每個子網路280台主機
 * 一個遮罩符合：172.16.0.0/24，200個子網路，每個子網路180台主機
 * 多個遮罩符合：172.16.0.0/22、23、24，50個子網路，每個子網路180台主機