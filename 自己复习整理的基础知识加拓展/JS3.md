#### json

- str.stringfy()对象、数组转换为json数据
- JSON.parse() json数据转换为数组或对象

![](image/7.png)

#### 事件流

- IE：事件冒泡流：事件最开始由最具体的元素（文档中嵌套最深的那个节点）接收，然后逐级向上。


- 另一个公司：事件捕获流：不太具体的节点应该更早接收到事件，而最具体的节点最后接收到事件

事件处理程序

- HTML事件响应处理：把事件直接添加在html元素上面，js与html紧密结合在一起，修改太麻烦。

- DOM0级事响应件处理：把一个函数赋值给一个事件的处理程序属性：简单，跨浏览器。（获取DOM元素，）

  `btn.onclick=function(){}`

- DOM2级事件响应处理：定义了两个方法

  addEventListener()  removeEventListener()

  接收三个参数：要处理的事件名，函数，布尔值（true为捕获阶段；false为冒泡阶段）

### IE事件处理程序

attachEvent()添加事件

detachEvent()删除事件

接收相同的两个参数：事件名称、函数

### 跨浏览器的事件处理程  序

![](image/8.png)

http请求

- HTTP请求的方法或者动作，get还是post
- 请求的URL
- 请求头
- 请求体：正文

![](image/9.png)

HTTP响应

- 状态码  请求成功还是失败
- 响应头
- 响应体，响应正文

![](image/10.png)

响应状态码

- 1XX 信息类，正在处理
- 2XX成功
- 3XX：重定向，表示请求没有成功
- 4XX：客户端错误，引用文档不存在
- 5XX：服务器错误，不能对请求作出处理

![](image/11.png)

![](image/12.png)

#### let变量和const常量的特性--不进行变量提升特性

- let const不能重复声明


### 解构赋值

```
let [x, , y] = [1, 2, 3];
console.log(x,y);//1 3

let [head, ...tail] = [1, 2, 3, 4];
console.log(head,tail);//1 [2, 3, 4]
注意：如果解构不成功，变量的值就等于undefined
```

```
//解构赋值中的默认值
var [foo3 = true] = [];//foo3 为 true
[x3, y3 = 'b'] = ['a']; // x3='a', y3='b'
[x4, y4 = 'b'] = ['a',undefined]; // x4='a'y4='b'
```

### 数组去重

```
var set = new Set([1, 2, 3, 4, 4]);
console.log([...set]);// [1, 2, 3, 4]
```

#### ES6提供了新的数据结构Set,通过add方法向Set结构加入成员，Set结构不会添加重复的值

~~~
//...也可以将set转换成数组
console.log([...(new Set([1, 2, 3, 4, 5]))]);//[1, 2, 3, 4, 5]
//如果不加[]就是散列的元素
console.log(...(new Set([1, 2, 3, 4, 5])));//1, 2, 3, 4, 5
~~~

### Promise

