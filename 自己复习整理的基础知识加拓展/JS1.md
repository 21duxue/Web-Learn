

# JavaScript

#### 五大基础类型（Symbal）+一大引用类型（Object）

- Number

- string

- null（只有一个值null）

- undefined（只有一个值undefined）

- Boolean（true  或  false)。

  > 函数

![](image/1.png)

（1-4）

- #### 字符串

  - –通过字符串变量的substr()方法，

    参数1：截取的开始位置下标；参数2：截取的长度（可选）

  ![](./image/2.png)


- #### 遍历对象

  for (var key in obj) 其中key代表键值，冒号前面的

- ​


![](image/3.png)

- ​

![](image/4.png)

- #### 字符串提取方法

  - str.slice(start,end)从start下标到end下标，slice(index)从index下标开始截取之后的。
  - str.split(str,num)通过指定分隔符对字符串进行切片,str -- 分隔符，默认为所有的空字符，包括空格、换行(\n)、制表符(\t)等;num -- 分割次数。默认为 -1, 即分隔所有。(num参数可不加)
  - str.substr(start,length)；str必需。要抽取的子串的起始下标。必须是数值，length可选。子串中的字符数。必须是数值。如果省略了该参数，那么返回从 *stringObject* 的开始位置到结尾的字串。
  - str.indexOf(searchvalue,fromindex)该方法将从头到尾地检索字符串 stringObject，看它是否含有子串 searchvalue。开始检索的位置在字符串的 fromindex 处或字符串的开头（没有指定 fromindex 时）。如果找到一个 searchvalue，则返回 searchvalue 的第一次出现的位置。stringObject 中的字符位置是从 0 开始的。

- #### 所有的对象转换布尔值都是真值

- #### 一般函数中的this（严格模式）为undefined，非严格下为全局变量

  ### 匿名函数的好处

  - 非匿名函数在定义就已经创建对象和作用域对象，未调用也会占用空间；匿名函数只有在调用在占用内存，调用完就释放空间了。比非匿名函数更节省空间。

- ### this指的什么

  ![](image/5.png)

  - call()的使用

    ![](image/6.png)

- #### JS函数调用时实参数量可以与形参不一致

  - 实参大于形参数量，通过函数对象属性arguments获得所有实参，类数组对象
  - 实参小于形参数量，少的参数为undefined

- #### 实参为基本数据类型时，形参改变不影响实参，实参为引用数据类型时，形参改变影响实参改变。

  闭包下一个










