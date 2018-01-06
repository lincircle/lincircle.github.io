## markdown 語法筆記

title 大小 
用法 ： 井字號後面，需要打空白鍵，才會變大

#h1 Heading

##h2 Heading

###h3 Heading

####h4 Heading

#####h5 Heading

######h6 Heading
 
Horizontal Rules

---- 
----
***

上面為一條線表示法

Emphasis

接下來唯一些斜線 粗體線的用法

Emphasis, aka italics, with *asterisks* or _underscores_.

Strong emphasis, aka bold, with **asterisks** or __underscores__.

Combined emphasis with **asterisks and _underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~

需要換行是兩格空白和一個 return 

## 裡面可以放 html 的 code  

Paragraph in Markdown.

<div class="class">
tyuioghjk
</div>

<div class="class">
<p style="background-color:Tomato;">Lorem ipsum...</p>
</div>

Paragraph in Markdown.

## Blockquotes 引用框框

> **Fusion Drive** combines a hard drive with a flash storage (solid-state drive) and presents it as a single logical volume with the space of both drives combined.  


### 可以雙引用 
  

> Donec massa lacus, ultricies a ullamcorper in, fermentum sed augue.
Nunc augue augue, aliquam non hendrerit ac, commodo vel nisi.
>> Sed adipiscing elit vitae augue consectetur a gravida nunc vehicula. Donec auctor
odio non est accumsan facilisis. Aliquam id turpis in dolor tincidunt mollis ac eu diam.

## Lists類型

+ Facilisis in pretium nisl aliquet
+ Nulla volutpat aliquam velit
  - Phasellus iaculis neque
  - Purus sodales ultricies
  - Ac tristique libero volutpat at
+ Faucibus porta lacus fringilla vel


1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa 

跟箭頭不一樣的區塊

``` markup
Sample text here...  
fjoij
```
Inline `code` has `back-ticks around` it.
上面

也有支援不同語法類型
用法：三個點點後 ＋ 語法 ＋ return 就好了

```js
grunt.initConfig({
  assemble: {
    options: {
      assets: 'docs/assets',
      data: 'src/data/*.{json,yml}',
      helpers: 'src/custom-helpers.js',
      partials: ['src/partials/**/*.{hbs,md}']
    },
    pages: {
      options: {
        layout: 'default.hbs'
      },
      files: {
        './': ['src/templates/pages/index.hbs']
      }
    }
  }
};
```

```swift
print("456789");
```

## 表格 table  

| Option | Description |
| ------ | ----------- |
| data   | path to data flates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |
向右對齊的功能
| Option | Description |
| ------:| -----------:|
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |
 
 ## Link
 一般加連結
[Assemble](http://assemble.io)
有加 title 的  

[Upstage](https://github.com/upstage/ "Visit Upstage!")

<http://yahoo.com.tw>

 ## Named Anchors
跳到同篇文章的地方

# Table of Contents
  * [Chapter 1](#chapter-1)
  * [Chapter 2](#chapter-2)
  * [Chapter 3](#chapter-3)

## Chapter 1 <a id="chapter-1"></a>
Content for chapter one.

## Chapter 2 <a id="chapter-2"></a>
Content for chapter one.

## Chapter 3 <a id="chapter-3"></a>
Content for chapter one.  
  
## Image 

![Minion](http://octodex.github.com/images/minion.png)

可以加 title 的

![Alt text](http://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")

![Alt text][id] 

[id]: http://octodex.github.com/images/dojocat.jpg  "The Dojocat"

加入 youtube 影片
[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/Th0s3p1bSgk/0.jpg)](http://www.youtube.com/watch?v=Th0s3p1bSgk)


