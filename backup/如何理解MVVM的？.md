是Model-View-ViewModel的缩写。前端开发的架构模式
        M：模型，对应的就是data的数据
        V：视图，用户界面，DOM
        VM：视图模型：Vue的实例对象，连接View和Model的桥梁
        核心是提供对View和ViewModel的双向数据绑定，当数据改变的时候，ViewModel能监听到数据的变化，自动更新视图，当用户操作视图的时候，ViewModel也可以监听到视图的变化，然后通知数据进行改动，这就实现了双向数据绑定
        ViewModel通过双向绑定把View和Model连接起来，他们之间的同步是自动的，不需要认为干涉，所以我们只需要关注业务逻辑即可，不需要操作DOM，同时也不需要关注数据的状态问题，因为她是由MVVM统一管理

[上一篇](https://hyramxue.github.io/post/v-if-he-v-show-de-qu-bie-%EF%BC%9F.html)
[下一篇](https://hyramxue.github.io/post/v-for-zhong-de-key-zhi-de-zuo-yong-shi-shen-me-%EF%BC%9F.html)