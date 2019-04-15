![](image/13.png)

#### 1、[call()、apply()的区别](https://www.cnblogs.com/lengyuehuahun/p/5643625.html)

### 2、[浏览器的工作原理](https://www.html5rocks.com/zh/tutorials/internals/howbrowserswork/)

### 3、[大数相加](https://www.jianshu.com/p/c51d63028371)

```
function addbignum(a,b){
		var arr_a = (a+'').split('');
		var arr_b = (b+'').split('');
		console.log(arr_a,arr_b)
		var lena = arr_a.length;
		var lenb = arr_b.length;
		var len = lena>=lenb?lena:lenb;
		console.log(len)
		var jin = 0;
		var sum = [];
		for(var i = 0;i<len;i++){
			if(lena-i-1>=0){
				var a = parseInt(arr_a[i]);
			}else{
				a=0;
			}
			if(lenb-i-1>=0){
				var b = parseInt(arr_b[i]);
			}else{
				b=0;
			}
		sum[i] = (a+b+jin)%10;
		jin =  parseInt((a+b+jin)/10);
		}
		console.log(sum);
		console.log(sum.reverse().join(''));
		return sum.reverse().join('');
	}
```



### 4、[闭包](https://baike.baidu.com/item/%E9%97%AD%E5%8C%85/10908873?fr=aladdin)

### 5、[HTTP请求+cookie的交互流程](https://www.cnblogs.com/bq-med/p/8603664.html)

### 6、[xxs攻击](https://www.freebuf.com/articles/web/185654.html)

### 7、[深拷贝、浅拷贝](https://www.cnblogs.com/echolun/p/7889848.html)

### 8、[angular双向数据绑定](https://blog.csdn.net/yiyan12/article/details/79616801)

.angular的数据绑定采用什么机制？详述原理

双向数据绑定是 AngularJS 的核心机制之一。当 view 中有任何数据变化时，会更新到 model ，当 model 中数据有变化时，view 也会同步更新，显然，这需要一个监控。

原理就是，Angular 在 scope 模型上设置了一个监听队列，用来监听数据变化并更新 view 。每次绑定一个东西到 view 上时 AngularJS 就会往 $watch 队列里插入一条 $watch ，用来检测它监视的 model 里是否有变化的东西。当浏览器接收到可以被 angular context 处理的事件时， $digest 循环就会触发，遍历所有的 $watch ，最后更新 dom。

2 AngularJS的数据双向绑定是怎么实现的？

1、每个双向绑定的元素都有一个watcher

2、在某些事件发生的时候，调用digest脏数据检测。

这些事件有：表单元素内容变化、Ajax请求响应、点击按钮执行的函数等。

3、脏数据检测会检测rootscope下所有被watcher的元素。

$digest函数就是脏数据监测

### 9、[CSS清除浮动](https://www.cnblogs.com/ForEvErNoME/p/3383539.html)

### 10、[react生命周期](https://www.cnblogs.com/qiaojie/p/6135180.html)

### 11、[angular生命周期](https://segmentfault.com/a/1190000012180793)

12、1.bind()函数只能针对已经存在的元素进行事件的设置；但是live(),on(),delegate()均支持未来新添加元素的事件设置

2.bind()函数在jquery1.7版本以前比较受推崇，1.7版本出来之后，官方已经不推荐用bind()，替代函数为on(),这也是1.7版本新添加的函数，同样，可以

3.live()函数和delegate()函数两者类似，但是live()函数在执行速度，灵活性和CSS选择器支持方面较delegate()差些，想了解具体情况，请戳这　http://kb.cnblogs.com/page/94469/

4.bind()支持Jquery所有版本；live()支持jquery1.9-；delegate()支持jquery1.4.2+；on()支持jquery1.7+；

[JQ事件绑定](https://blog.csdn.net/zhang070514/article/details/76778920/)

### 12、[BFC(块级格式化上下文)](https://segmentfault.com/a/1190000013647777)

### 13、MVC，MVP，MVVM

- MVC：用户操作view, 用户操作View去改变Controller，Controller改变Model, Model再直接根据业务代码显示在View上。

  ​优点是 当时极大程度降低了页面与逻辑的耦合性

- MVVM
- MVP
- `shouldComponentUpdate` -- 如果你担心组件过度渲染，`shouldComponentUpdate` 是一个改善性能的地方，因为如果组件接收了新的 `prop`， 它可以阻止(组件)重新渲染。shouldComponentUpdate 应该返回一个布尔值来决定组件是否要重新渲染


### 14为什么还用redux

- 组件需要根据状态发生显示变化
- state并不总是以单向的方式线性流动
- 存在组件需要更新全局状态
- 存在组件需要更新另一个组件的状态
- 存在状态以许多不同的方式更新
- 状态树结构复杂
- 某个状态需要在全局使用或共享（例如角色权限等信息）

当 props 和 state 发生变化时，React会根据shouldComponentUpdate方法来决定是否重新渲染整个组件。

### 15、原生js实现map方法

我们平时用的是已经封装好的map方法，如果让我们自己封装一个map，应该如何实现。
万变不离其宗，其实遍历数组的核心还是for循环。因此下面封装一个map方法。
思路：
1.在原型上添加一个方法
2.传一个函数和this
3.call 方法传的参数和封装好的map方法的参数是一样的。

	Array.prototype.fakeMap = function(fn,context) {
	let arr = this;
	let temp = [];
	for(let i=0;i<arr.length;i++){
		let result = fn.call(context,arr[i],i,arr);
		temp.push(result);
	}
	return temp;
	}
#### [JS Array.reduce 实现 Array.map 和 Array.filter](https://juejin.im/post/5c0b7f03e51d452eec725729)

```
const reduceMap = (fn, thisArg /*真想去掉thisArg这个参数*/ ) => {
        return (list) => {
            // 不怎么愿意写下面这两个判断条件
            if (typeof fn !== 'function') {
                throw new TypeError(fn + 'is not a function')  
            }
            if (!Array.isArray(list)) {
                throw new TypeError('list must be a Array')
            }
            if (list.length === 0) return []
            return list.reduce((acc, value, index) => {
                return acc.concat([ fn.call(thisArg, value, index, list) ])
            }, [])
        }
    }
```






