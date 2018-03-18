# 数组(Array)常用的操作方法

Array对象是用于构造数组的全局对象。

**创建数组**
```

var person = [1,2,3]
console.log(person.length)
//3

var b = Array(1,2,3,4,)
console.log(b.length)
//4
```
**访问数组和赋值**
```
//通过下标访问，下标从0开始。
var person = [1,2,3]
person[0]  // 1
person[1]  // 2
person[2]  // 3

person[2]  = 30  // 赋值
person  //1,2,30

person.length = 0  //清空数组
console.log(person)  //[]

```
**遍历数组**
```
//item 值 
//index 下标
//array 数组
var person = [1,2,3]
person.forEach(function(item,index,array){
console.log(item,index)
})
// 1 0
// 2 1
// 3 2
```

**push()添加元素到数组末尾**
```
var a = [1,2,3]
a.push(5) //添加5到数组末尾，结果返回长度 4

console.log(a)  //[1,2,3,5]
```
**pop()删除数组末尾的元素** 

```
var a = [1,2,3]
a.pop()  //3
console.log(a) //[1,2]
```
**shift()删除数组头部的元素**
```
var a = [1,2,3]
a.shift() //1
console.log(a)//[2,3]
```
**unshift()添加元素到数组头部**
```
var a = [1,2,3]
a.unshift(4) //4
console.log(a) //[4,1,2,3]
```
**indexOf()找出某个元素在数组中的索引**
```
var a = [1,2,3,4,5,6,7,9]
a.indexOf(4) //3
```
**splice()从下标M开始向右删除N个元素,且在下标M添加新元素(可选)。**
```
var a = [1,2,3,4,5,6,7]
a.splice(2,3,999) //[3,4,5]
console.log(a) // [1,2,999,6,7]
```
**slice() 复制数组。从下标M开始带下标N结束(不包括下标N),作为一个新数组。原数组不变。**
```
var a = [1,2,3,4] 
var b = a.slice(1,3)

a //[1,2,3,4]
b //[2,3]
```
**concat()连接两个或更多的数组，并返回结果。被连接的数组不变。**
```
var a = [1,2,3]
var b = [4,5,6]
var c = a.concat(b)  

console.log(a) // [1,2,3]
console.log(b) // [4,5,6]
console.log(c) // [1,2,3,4,5,6]
```

**reverse() 将数组逆序。会改变原数组。**

```
var a = [1,2,3]
var b = a.reverse()

console.log(a) // [3,2,1]
console.log(a) // [3,2,1]
a === b //true
```
**sort()对数组进行排序。**

1、没有参数会按字母表升序排序。

2、自定义函数

3、如果含有undefined会被排到最后面，对象元素则会调用其toString方法。
```
var a=[5,4,3,2,1]
a.sort()
console.log(a) //[1, 2, 3, 4, 5]

var a=[7,8,9,10,11]
a.sort()
console.log(a) //[10, 11, 7, 8, 9]

因为按照字母表排序，7就比10大了

自定义函数：

 var a = [7,8,9,10,11]

    a.sort(function(v1,v2){
        return v1-v2
    })
    console.log(a) //[7, 8, 9, 10, 11]

    var users = [
        {
            name: 'aaa',
            age: 21
        },
        {
            name: 'baa',
            age: 18
        },
        {
            name: 'abc',
            age: 24
        }
    ]

    // 按age 从小到大排序
    var sortByAge = users.sort(function(v1, v2){
        return  v1.age > v2.age
    })
//[{name: 'baa',age: 18},{ name: 'aaa',age: 21},{ name: 'abc',age: 24}]

  // 按name从大到小排序
    var sortByName = users.sort(function(v1, v2){
        return  v1.name > v2.name
    })
//[{name: "aaa", age: 21},{name: "abc", age: 24},{name: "baa", age: 18}]

```
**toString() 把数组转换成字符串**
```
var a = [1,2,3,4]
a.toString()
//"1,2,3,4"
```
**split()将一个[`String`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/String "此页面仍未被本地化, 期待您的翻译!")对象分割成字符串数组。**
```
var a ="1234"
a.split("")
//["1","2","3","4"]

-----------------------------------
var a ="1,2,3,4"
a.split("")

//["1", ",", "2", ",", "3", ",", "4", ","]

//优化：
var names = "1,23,4";

var re = /\s*,\s*/;
var nameList = names.split(re);

console.log(nameList);//["1","23","4"]


```




## Array 对象方法与作用

|方法名称|说明|
|:-:|:-------:|
|push|向数组的末尾添加一个或更多元素，并返回新的长度 a.push(5)|
|pop|删除并返回数组中的最后一个元素 a.pop()|
|shift|删除并返回数组中的第一个元素 a.shift()|
|unshift|添加并返回数组中的第一个元素 a.unshift()|
|indexOf|找出某个元素在数组中的索引，并返回该元素索引。|
|splice|从下标M开始向右删除N个元素,且在下标M添加新元素(可选)。|
|slice|复制数组(浅拷贝)。从下标M开始带下标N结束(不包括下标N),作为一个新数组。原数组不变。|
|concat|连接两个或更多的数组，并返回结果。被连接的数组不变。|
|reverse|将数组逆序。会改变原数组。|
|sort|对数组进行排序|
|join|把数组的所有元素放入一个字符串，元素通过制定的分隔符进行分离 arr1.join(',')|
|toString|把数组转成字符串 arr1.toString()|
|toLocaleString|把数组转换为本地字符串 arr1.toLocaleString()|
|split|将string对象分割成字符串数组。|
|valueOf|返回数组对象的原始值|

更多请看[MDN](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array)


