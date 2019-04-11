#### 生成对象的三种方式

- 字面值（直接创建）
- 运用构造函数创建
- Object工场方法`var obj = Object.create(objProto);`

#### 判断对象自身属性是否存在

-  Object.prototype.hasOwnProperty() 判断自身是否有该属性，包括不可枚举的属性

-  Object.prototype.propertyIsEnumerable() 判断自身是否有该属性并检测该属性是否可枚举

     ​

#### this

- 一般函数中的this，一般指代全局对象（严格模式下指代undefined）

- 对象方法中的this：对象方法中的this指代调用此方法的对象（无嵌套的情况下）

- 构造函数中的this：构造函数中的this指代通过new新创建的对象

- 通过call/applay间接调用的函数中的this（指代第一个参数）

  ```
  var bird = {
      name:"polly",
      fly:function(m,n){
          console.log("i'm:"+this.name+" i can fly ___",m,n);
      }
  };
  var me = {
      name:"QL"
  };
  bird.fly(5,6);
  bird.fly.call(me,7,8);
  ```

#### 如何解决对象方法中嵌套函数的this指向问题

- 使用变量（that或self）软绑定，使this指向正确

  ```
  var point = {
      x:0,
      y:0,
      moveTo:function (x,y) {
          var that = this;//关键的一行，软绑定
          //内部嵌套函数
          function moveToX() {
              that.x = x;//this改为that
          }
          //内部嵌套函数
          function moveToY() {
              that.y = y;//this绑定到了哪里？
          }
          moveToX();
          moveToY();
      }
  };
  point.moveTo(2,2);
  console.log(point);
  ```

- •方法二：使用call/apply间接调用，使this指向正确

  ```
  var point = {
      x:0,y:0,
      moveTo:function (x,y) {
          function moveToX() {
              this.x = x;//this绑定到了哪里？
          }
          function moveToY() {
              this.y = y;//this绑定到了哪里？
          }
          moveToX.call(this);//->this.moveToX()->point.MoveToX()
          moveToY();
      }
  };
  point.moveTo(2,2);console.log(point);//2,0
  ```


- •方法三：使用Function.prototype.bind，使this指向正确

  ```
  var point = {
      x:0,y:0,
      moveTo:function (x,y) {
          function moveToX() {
              this.x = x;//this绑定到了哪里？
          }
          function moveToY() {
              this.y = y;//this绑定到了哪里？
          }
          moveToX.bind(point)();
          moveToY.bind(point)();
      }
  };
  point.moveTo(2,2);
  console.log(point);
  ```

#### 数组的方法

- 颠倒`arr.reverse()`颠倒数组

- 排序  `arr.sort()` 给数组排序

- 拼接 `arr1.concat(arr2)`给数组arr1和arr2拼接

- 切分 `arr.slice(begin,end)`  从数组的begin下标开始切，一直到end；end没有的话，从begin一直到最后；

- `arr.join('str')` 数组转化成字符串，数组之间用str连接。

  ```
  var arr7 = [3,4,5];
  var joinReturn = arr7.join("--");
  //其中joinReturn为3--4--5 
  ```

- splice() 方法用于添加或删除数组中的元素。**注意：**这种方法会改变原始数组。

  `*array*.splice(*index*,*howmany*,*item1*,.....,*itemX*)`

  index(必须):规定从哪添加/删除元素，数组下标

  howmany(必需)：规定应该删除多少元素。必须是数字，但可以是 "0"。

  规定应该删除多少元素。必须是数字，但可以是 "0"。
  如果未规定此参数，则删除从 index 开始到原数组结尾的所有元素。

  ```
  var fruits = ["Banana", "Orange", "Apple", "Mango"];
  fruits.splice(2,1,"Lemon","Kiwi");
  输出结果：Banana,Orange,Lemon,Kiwi,Mango
  ```

- push() 方法可向数组的末尾添加一个或多个元素，并返回新的长度

- pop()删除数组的最后一个元素并返回删除的元素。

- shift()删除并返回数组的第一个元素。

- indexOf() 方法可返回某个指定的字符串值在字符串中首次出现的位置。

- Array.from() 可将类数组对象或可遍历的对象（包括Map）转换为数组

- Array.of( )  可将一组值，转换为数组，弥补数组构造函数Array()的不足


### 正则表达式

- g表示全局，加i表示不区分大小写。

- .是指任意1个字符; *是指0个或多个

- \b表示边界   \B表示非边界

- \d匹配一个数字等价于[0-9] ，\D匹配一个非数字等价于[ ^0-9]

- \w匹配一个单字字符（字母、数字或者下划线）。等价于[A-Za-z0-9_]。

  \W匹配一个非单字字符。等价于[ ^A-Za-z0-9_]。

- [ ]代表字符类，如[abc]代表abc中的任意一个字符

- [^]代表字符类取反，如[^abc]代表非abc中的任意一个字符

- ？出现0次或1次（最多1次）  +出现1次或多次（至少1次）   *出现0次或多次（任意次）
  {n} 出现n次       {n,m} 出现n到m次      {n,}出现至少n次

- #### 贪婪模式和非贪婪模式

  ```
  "12345678".replace(/\d{3,6}/,'X');//默认为贪婪模式  X78
  "12345678".replace(/\d{3,6}?/,'X');//设置为非贪婪模式 在量词后加？X45678
  ```

- lastIndex表示当前匹配内容的最后一个字符的下一个位置

  #### 正则表达式方法

- test().判断是否有这个匹配，如果是全局lastindex会不断变化。对于非全局模式下返回第一个匹配的和所有的分组项，正则对象的lastIndex不起作用


- exec():对于全局模式下 每检测一次lastIndex增加一次，再次用此正则对象匹配时，匹配的起始点为上一次的lastIndex

  ```
  var execExp2 = /\d{1,2}(\d)(\d)/g;
  var ts = "12s342dsfsf233s";
  console.log(execExp2.exec(ts),execExp2.lastIndex);
  //lastIndex为 6
  console.log(execExp2.exec(ts),execExp2.lastIndex);
  //lastIndex为 14
  ```

- match():如果匹配不到返回null 匹配到了返回数组

  ```
  console.log("a1b2c3d4".match(/\d/));//[ '1', index: 1, input: 'a1b2c3d4' ]
  console.log("a1b2c3d4".match(/\d/g));//[ '1', '2', '3', '4' ]
  ```

  ​

  ​

  ​

  ​