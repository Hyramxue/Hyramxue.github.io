Vue实例从创建到销毁的过程，称为Vue的生命周期
- beforeCreate：实例初始化之前，此阶段为实例添加了一些如data属性、methods属性等。

- created：实例创建完成后，在这一步，实例已完成以下的配置：数据观测 (data observer)，属性和方法的运算，watch/event事件回调。然而，挂载阶段还没开始，$el属性目前不可见。

- beforeMount：模板编译之前，此时还没有DOM节点。

- mounted：模板编译之后，此时DOM已经挂载，可以访问到DOM元素。

- beforeUpdate：在数据更新之前执行，此时DOM仍然是更新前的。

- updated：在数据更新之后执行，此时DOM已经更新。

- beforeDestroy：实例销毁之前调用，此时实例仍然完全可用。

- destroyed：实例销毁后调用，此时所有的事件监听器会被移除，所有的子实例也会被销毁。

[上一篇](https://hyramxue.github.io/post/v-for-zhong-de-key-zhi-de-zuo-yong-shi-shen-me-%EF%BC%9F.html)
[下一篇](https://hyramxue.github.io/post/zai-created-he-mounted-qu-qing-qiu-shu-ju-%EF%BC%8C-you-shen-me-qu-bie-%EF%BC%9F.html)