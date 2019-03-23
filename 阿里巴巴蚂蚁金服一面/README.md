# 蚂蚁金服一面
- #### 自我介绍

- ### 网络原理方面

  - ##### [TCP三次握手、四次挥手](https://blog.csdn.net/ZWE7616175/article/details/80432486)

    ![](https://img-blog.csdnimg.cn/20190214095421560.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1pXRTc2MTYxNzU=,size_16,color_FFFFFF,t_70)

    - 为什么连接的时候是三次握手，关闭的时候却是四次握手？

      ###### 答：因为当Server端收到Client端的SYN连接请求报文后，可以直接发送SYN+ACK报文。其中ACK报文是用来应答的，SYN报文是用来同步的。但是关闭连接时，当Server端收到FIN报文时，很可能并不会立即关闭SOCKET，所以只能先回复一个ACK报文，告诉Client端，"你发的FIN报文我收到了"。只有等到我Server端所有的报文都发送完了，我才能发送FIN报文，因此不能一起发送。故需要四步握手。

  - ##### [TCP 、UDP原理，作用区别.](https://www.cnblogs.com/xiaomayizoe/p/5258754.html)

  - ##### [从浏览器输入URL开始到渲染到页面这个流程](https://www.cnblogs.com/KevinGeorge/p/10198505.html)

  - ##### [cookie和session的底层原理，区别，储存在具体哪个位置。](https://www.cnblogs.com/endlessdream/p/4699273.html)

    - session存储位置
      - 内存文本文件
      - 数据库

  - ##### [HTTP状态码](https://github.com/huyaocode/webKnowledge/blob/master/%E7%BD%91%E7%BB%9C/HTTP.md)

  - ##### [HTTP和HTTPS的区别，原理](https://www.cnblogs.com/wudaoyongchang/p/6253451.html)

  - ##### [缓存：强缓存+弱缓存](https://segmentfault.com/a/1190000008956069)

- ### web安全方面

  - ##### CSRF攻击、XSS攻击原理及解决办法（结合cookie+session）

    - [XSS攻击](https://www.jianshu.com/p/630363a28549)
    - [CSRF攻击](https://www.cnblogs.com/phpstudy2015-6/p/6771239.html)
    - ([CSRF攻击的防御](https://blog.csdn.net/xiaoxinshuaiga/article/details/80766369))

  - ##### [跨域的方式及原理](https://segmentfault.com/a/1190000011145364)

- ### 性能优化

  - ##### [CDN原理](https://www.cnblogs.com/Ron-Zheng/p/webclientCdn.html)

  - ##### [在后端，选择java、nodejs、Python作为后端开发语言，都有什么好处？](https://blog.csdn.net/herobacking/article/details/82721242)

  - ##### [性能优化的措施](https://www.cnblogs.com/MarcoHan/p/5295398.html)

- ### JS基础

  - ##### [什么是闭包，可以解决什么问题一般在哪使用](https://www.cnblogs.com/171220-barney/p/8552370.html)

    ##### [js闭包解决多个点击事件](https://www.cnblogs.com/maxigang/p/5578040.html)


- ##### [数组去重（多种方式）](https://blog.csdn.net/qq_38989725/article/details/81006998)

- ##### [call  bind   apply区别](https://blog.csdn.net/wyyandyou_6/article/details/81488103)

- ##### [如何使用js实现链表](https://www.cnblogs.com/EganZhang/p/6594830.html)

- ##### 继承

- ##### [深拷贝与浅拷贝解释，以及如何实现](https://www.cnblogs.com/echolun/p/7889848.html)

- ### 其他

  - ##### webpack的了解

  - ##### [设计模式](https://www.cnblogs.com/yangguoe/p/8459312.html)


- ##### 数据结构排序算法

- ##### [有没有看过angular或者react底层源码，比如双向数据绑定原理](https://blog.csdn.net/momdiy/article/details/78856878)

