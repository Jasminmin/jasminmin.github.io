---
layout: post
title: Markdown怎麼用？常見指令大集合
subtitle: 用github架設的Jekyll網站該如何撰寫文章
gh-repo: daattali/beautiful-jekyll
gh-badge: [star, fork, follow]
tags: [tech, markdown]
comments: true
---

Markdown是什麼呢 ( ・◇・)？<br>
維基百科解釋如下：<br>
> Markdown 是一種輕量級標記式語言，創始人為約翰·格魯伯（John Gruber）。它允許人們「使用易讀易寫的純文字格式編寫文件，然後轉換成有效的XHTML(或者HTML)文件」。

簡而言之，Markdown是讓我們可以不用撰寫落落長的HTML語法而產生的標記式語言 ƪ(˘⌣˘)ʃ<br>
舉個栗子🌰，網頁編輯時如果需要一個列表，HTML撰寫方式如下：

```html
<ul>
  <li style="text-align: left;"><b>這是標題</b></li>
  <ul>
    <li style="text-align: left;">這是列表一</li>
  </ul>
  <ul>
    <li style="text-align: left;">這是列表二</li>
  </ul>
<ul>
```
如果使用Markdown，我們只需要撰寫：
```markdown
* 這是標題
  * 這是列表一
  * 這是列表二
```

以上兩種撰寫方式所呈現的效果都是：
* 這是標題
  * 這是列表一
  * 這是列表二

就是這麼好用！！！接下來就介紹我們常見的markdown語法吧～

__________

### <font color="#6495ED">段落與換行</font>
1. 段落：於文章中如需分開章節切割段落，需「換行」。
2. 換行：於文中段落中如需換行，可於句末輸入**< br >**。

### <font color="#6495ED">字體樣式及標題</font>
1. 粗體字<br>
  * Code<br>
```
**This is Bold text**
```
  * Example<br>
**This is Bold text**
2. 斜體字
  * Code<br>
```
_This is Italics text_
*This is Italics text*
```
  * Example<br>
_This is Ittalics text_
3. 刪除線
  * Code<br>
```
~~This is Deleted text~~
```
  * Example<br>
~~This is Deleted text~~
5. 標題大小
  * Code<br>
```
# This is <h1> Header.
## This is <h2> Header.
### This is <h3> Header.
#### This is <h4> Header.
```
  * Example<br>
# This is <h1> Header.
## This is <h2> Header.
### This is <h3> Header.
#### This is <h4> Header.

### <font color="#6495ED">清單列表</font>
1.數字階層<br>
```
#以數字開頭「.」符號做區隔，符號後需空格
1. 第1層
  1. 第1-1層
  2. 第1-2層
2. 第2層
  1. 第2-1層
```
2.符號階層<br>
```
+ 第1層
  * 第1-1層
  * 第1-2層
+ 第2層
  * 第2-1層
```

### <font color="#6495ED">區塊引言</font>
1. 區塊
Code<br>
```
#前後加上「`」，可用於小段程式碼
`Format one word or one line`
```
Example<br>
`Format one word or one line`
2. 引言
Code<br>
```
>第1層引言
>>第2-1層引言<br>
>>第2-2層引言
```
Example<br>
>第1層引言
>>第2-1層引言<br>
>>第2-2層引言

### <font color="#6495ED">程式碼</font>
Code<br>
```
＃程式碼段落輸入「```」，可註記為何種語言，以下範例將＃拿掉
#```javascript
var foo = function(x) {
  return(x + 5);
}
foo(3)
#```
```
Example<br>
```javascript
var foo = function(x) {
  return(x + 5);
}
foo(3)
```
以下為增加行數編號，更換```為「{o/o high1ight o/o} Code {o/o endhigh1ight o/o}」
{% highlight javascript linenos %}
var foo = function(x) {
  return(x + 5);
}
foo(3)
{% endhighlight %}
### <font color="#6495ED">Checkbox</font>
Code<br>
```
- [x] This is a complete item
- [ ] This is an incomplete item
```
Example<br>
- [x] This is a complete item
- [ ] This is an incomplete item

### <font color="#6495ED">超連結</font>
1. 網址連結
  * Code<br>
```
前往至[Google](https://www.google.com/)
```
  * Example<br>
前往至[Google](https://www.google.com/)
2. 圖片連結
  * Code<br>
```
#網址連結寫法前方加上！
![Alt text](/img/avatar-icon.png)
```
  * Example<br>
![Alt text](/img/avatar-icon.png){:width="50%"}

### <font color="#6495ED">表格</font>
Code<br>
```
| Number | Next number | Previous number |
| :------ |:--- | :--- |
| Five | Six | Four |
| Ten | Eleven | Nine |
| Seven | Eight | Six |
| Two | Three | One |
```
Example

| Number | Next number | Previous number |
| :------ |:--- | :--- |
| Five | Six | Four |
| Ten | Eleven | Nine |
| Seven | Eight | Six |
| Two | Three | One |

### <font color="#6495ED">Boxes</font>

* Notification：`{: .box-note}`

{: .box-note}
**Note:** This is a notification box.

* Warning：`{: .box-warning}`

{: .box-warning}
**Warning:** This is a warning box.

* Error：`{: .box-error}`

{: .box-error}
**Error:** This is an error box.

### <font color="#6495ED">分隔線</font>

Code<br>
```
#三個或以上的「 _ 」、「 - 」、「 * 」
___
***
---
```
Example<br>

___

以上，這些是常用的Markdown～<br>
大家在撰寫文章可以多利用，提高寫文章的速度<br>
但還是有些輔助設定還是要用HTML喔<br>
例如：圖片大小、文字顏色等等<br>
希望大家都喜歡這篇文章 (๑ↀᆺↀ๑)✧