---
layout: post
title: "[swift] map filter reduce 用法"
date: 2017-02-14 18:00:00
---

因最近比較常接觸這些函數來處理 `Array`，此篇主要是想釐清下面幾個函數的用法，熟悉之後就可以減少使用 for 迴圈

* ### filter

* ### map

* ### reduce

* ### flatMap

* ### contains

> 下面出現的 `$0` 、 `$1` ⋯⋯，分別代表第一個傳入的參數與第二個參數，以此類推。

### filter

> 將陣列裡面符合條件的元素，放置在一個新的陣列。

{% highlight swift linenos %}

var digits = [1,4,10,15]

let array = digits.filter{ $0 < 5 }

//array = [1, 4]

{% endhighlight %}


### map

> 像是函數式 F(x) 一樣，需要將`Array`的每個值取出帶入所設定的條件，產生出新的值。

{% highlight swift %}

let cast = ["Vivien", "Marlon", "Kim", "Karl"]

let letterCounts = cast.map { $0.characters.count }

// 'letterCounts' == [6, 6, 3, 4]

{% endhighlight %}

上述的例子是將 `cast Array` 中的每個元素取出來算組成每個單字的字母有幾個，得出新的值再放入 `letterCounts Array` 。

{% highlight text %}

let digits = [1,4,10,15]

let squares = digits.map{ (element) -> Int in return element * element}

// squares = [1, 16, 100, 225]

{% endhighlight %}

### reduce

> 會將 `Array` 裡面的值處理完後，回傳`一個值`。`reduce` 需要有兩個參數，一個為初始值，一個為 ` Closure` 裡面可以使用目前累加值與 Array 的元素。

{% highlight text %}

let numbers = [1, 2, 3, 4]

let numberSum = numbers.reduce(0, { x, y in

    x + y

})

// numberSum == 10

{% endhighlight %}

可以寫為

{% highlight text %}

let numbers = [1, 2, 3, 4]

let numberSum = numbers.reduce(0) { $0 + $1 }

// numberSum == 10

{% endhighlight %}

`初始值 ＝ 0`，X  為累加值，Ｙ 為目前迴圈索取出的元素。

{% highlight text %}

let string = ["a","b","c","d"]

let text = string.reduce("==>") { result , element  in"\(result),\(element)"}

// text 值為 ==>,a,b,c,d

{% endhighlight %}

也可以結合字串

### flatMap

> 有兩種不同的重載函數

第一種

{% highlight text %}

func flatMap<SegmentOfResult>(_ transform: (Element) throws -> SegmentOfResult) rethrows -> [SegmentOfResult.Iterator.Element] where SegmentOfResult : Sequence

{% endhighlight %}

> 會將多個 Array 變成一個 Array 。

{% highlight text %}

let collections = [[5,2,7],[4,8],[9,1,3]]

let flat = collections.flatMap { $0 }

// [5, 2, 7, 4, 8, 9, 1, 3]

{% endhighlight %}

第二種

{% highlight text %}

func flatMap<ElementOfResult>(_ transform: (Element) throws -> ElementOfResult?) rethrows -> [ElementOfResult]

{% endhighlight %}

> 會移除掉陣列裡面存在有 Optional 的值。

{% highlight text %}

let people: [String?] = ["Tom",nil,"Peter",nil,"Harry"]

let valid = people.flatMap {$0}

// ["Tom", "Peter", "Harry"]

{% endhighlight %}

### contains

> 如果有陣列裡面有符合條件值，將回傳 Bool

{% highlight text %}

let marks = [4,5,8,2,9,7]

let even = marks.contains(where: {

    if $0 % 2 == 0 {
        
        return true
    }
    else {
     
        return false
        
    }
})

//輸出為 true

{% endhighlight %}

可以簡化成

{% highlight text %}

let even = marks.contains(where: {$0 % 2 == 0})

{% endhighlight %}

參考資料：

[Use Your Loaf Blog](http://useyourloaf.com/blog/swift-guide-to-map-filter-reduce/)

[swift 學習筆記](https://hugolu.gitbooks.io/learn-swift/content/Advanced/HighOrderFunctions.html)

[Apple Developer - reduce](https://developer.apple.com/reference/swift/array/2298686-reduce)

[Apple Developer - flatMap](https://developer.apple.com/reference/swift/unsafebufferpointer/1688503-flatmap)

[Apple Developer - filter](https://developer.apple.com/reference/swift/array/1688383-filter)

[Apple Developer - map](https://developer.apple.com/reference/swift/array/1688519-map)

[Apple Developer - contains](https://developer.apple.com/reference/swift/anysequence/2295926-contains)

[Swift 烧脑体操（四） - map 和 flatMap](http://www.infoq.com/cn/articles/swift-brain-gym-map-and-flatmap)
