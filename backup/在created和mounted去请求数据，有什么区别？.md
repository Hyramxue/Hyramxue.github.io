- created：在渲染前调用，通常先初始化属性，然后做渲染
- mounted：在模板渲染完成后，一般都是初始化页面后，在对元素节点进行操作
                   在这里请求数据可能会出现闪屏的问题，created里不会
        一般用created比较多
        请求的数据对DOM有影响，那么使用created
        如果请求的数据对DOM无关，可以放在mounted


[上一篇](https://hyramxue.github.io/post/shuo-yi-xia-ni-dui-vue-sheng-ming-zhou-qi-de-li-jie-%E3%80%82.html)