localStorage存储超过最大值怎么办？

1. localStorage存储拿到的值，永远是字符串
2. localStorage存储大小是有限制的

-   解决方式一：把存储的值，进行压缩

   lz-string库

   优势：简单
   缺点：多引入一个库，如果我们localStorage存储的是很大（光靠压缩解决不来问题）

-   解决方式二：indexedDB

   indexedDB：本身操作比较繁琐、存在浏览器的兼容

   问题：本身操作比较繁琐，解决方案：localforage库

   优势：

    异步
    存储进入的值是什么类型，读取出来还是之前类型
    存储大小远远超过cookie和localStorage
