- 相同点
   都可以控制元素的显示和隐藏。

- 区别
1. v-show时控制元素的display值来让元素显示和隐藏；v-if显示隐藏时把DOM元素整个添加和删除;
2. v-if有一个局部编译/卸载的过程，切换这个过程中会适当的销毁和重建内部的事件监听和子组件；v-show只是简单的css切换;
3. v-if才是真正的条件渲染；v-show从false变成true的时候不会触发组件的生命周期，v-if会触发生命周期;
4. v-if的切换效率比较低  v-show的效率比较高。
 
[上一篇](https://hyramxue.github.io/post/localStorage-cun-chu-chao-guo-zui-da-zhi-zen-me-ban-%EF%BC%9F.html)
[下一篇](https://hyramxue.github.io/post/ru-he-li-jie-MVVM-de-%EF%BC%9F.html)