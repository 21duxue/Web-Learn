### 1、[高阶函数map、reduce、filter、sort](https://www.cnblogs.com/blogzxl/p/7017622.html)

### 2、实现一个类型判断函数

1. 判断null
2. 判断基础类型
3. 使用`Object.prototype.toString.call(target)`来判断**引用类型**

注意： 一定是使用`call`来调用，不然是判断的Object.prototype的类型
之所以要先判断是否为基本类型是因为：虽然`Object.prototype.toString.call()`能判断出某值是：number/string/boolean，但是其实在包装的时候是把他们先转成了对象然后再判断类型的。 但是JS中包装类型和原始类型还是有差别的，因为对一个包装类型来说，typeof的值是object

```javascript
/**
 * 类型判断
 */
function getType(target) {
  //先处理最特殊的Null
  if(target === null) {
    return 'null';
  }
  //判断是不是基础类型
  const typeOfT = typeof target
  if(typeOfT !== 'object') {
    return typeOfT;
  }
  //肯定是引用类型了
  const template = {
    "[object Object]": "object",
    "[object Array]" : "array",
    "[object Function]": "function",
    // 一些包装类型
    "[object String]": "object - string",
    "[object Number]": "object - number",
    "[object Boolean]": "object - boolean"
  };
  const typeStr = Object.prototype.toString.call(target);
  return template[typeStr];
}
```

### 3、事件循环（event loop）

[Event Loop 这个循环你晓得么？(附 GIF 详解)-饿了么前端](https://zhuanlan.zhihu.com/p/41543963)

### 4、[JavaScript垃圾回收机制](https://zhuanlan.zhihu.com/p/41543963)

### 5、[浅谈React的最大亮点——虚拟DOM](https://blog.csdn.net/zhouziyu2011/article/details/71171567)

### 6、[观察订阅模式](https://www.jianshu.com/p/9061b7da246a)

### 7、[angular双向数据绑定](https://blog.csdn.net/yiyan12/article/details/79616801)

### 8、[前端继承方式](https://www.cnblogs.com/greatluoluo/p/6273787.html)

### 9、[ajax跨域get post](https://blog.csdn.net/alokka/article/details/83060184)

### 10、[get和post的区别](https://www.cnblogs.com/logsharing/p/8448446.html)

