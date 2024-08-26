* 表单修饰符
  1. .lazy
     > v-model.lazy就可以吧这个同步事情变得懒惰, 只会在 `失去焦点`的时候进行数据同步
     >
  2. .trim
     > 自动过滤用户输入的首空格字符，而中间的空格不会过滤
     >
  3. .number
     > 自动将用户的输入值转为数值类型，但如果这个值无法被 `parseFloat`解析，则会返回原来的值
     >
* 事件修饰符
  1. .stop

     > 阻止了事件冒泡，相当于调用了event.stopPropagation方法
     >
  2. .prevent

     > 阻止了事件的默认行为（a标签跳转，表单提交等等），相当于调用了event.preventDefault方法
     >
  3. .self

     > 只当在 event.target 是当前元素自身时触发处理函数
     >

     > 重点：使用修饰符时，顺序很重要；相应的代码会以同样的顺序产生。因此，用 `v-on:click.prevent.self`会阻止所有的点击，而 `v-on:click.self.prevent`只会阻止对元素自身的点击
     >
  4. .once

     > 绑定了事件以后只能触发一次，第二次就不会触发
     >
  5. .capture

     > 使事件触发从包含这个元素的顶层开始往下触发
     >

     ```html
     <div @click.capture="shout(1)">
         obj1
         <div @click.capture="shout(2)">
             obj2
             <div @click="shout(3)">
                 obj3
                 <div @click="shout(4)">
                     obj4
                 </div>
             </div>
         </div>
     </div>
     // 输出结构: 1 2 4 3 

     ```
  6. .passive

     > 当我们在监听元素滚动事件的时候，会一直触发 `onscroll`事件会让我们的网页变卡，因此我们使用这个修饰符的时候，相当于给 `onscroll`事件整了一个.lazy修饰符
     >

     ```html
     <!-- 滚动事件的默认行为 (即滚动行为) 将会立即触发 -->
     <!-- 而不会等待 `onScroll` 完成  -->
     <!-- 这其中包含 `event.preventDefault()` 的情况 -->
     <div v-on:scroll.passive="onScroll">...</div>

     ```

     > 不要把 .passive 和 .prevent 一起使用,因为 .prevent 将会被忽略，同时浏览器可能会向你展示一个警告。passive 会告诉浏览器你不想阻止事件的默认行为
     >
  7. .native

     > 让组件变成像html内置标签那样监听根元素的原生事件，否则组件上使用 v-on 只会监听自定义事件
     >

     ```html
     <my-component v-on:click.native="doSomething"></my-component>

     ```
* 鼠标按键修饰符
  1. left 左键点击
  2. right 右键点击
  3. middle 中键点击
* 键值修饰符
  1. keyCode

     > 如果不用keyCode修饰符，那我们每次按下键盘都会触发shout，当我们想指定按下某一个键才触发这个shout的时候，这个修饰符就有用了，具体键码查看[键码对应表](https://zhidao.baidu.com/question/266291349.html)
     >

     > * 回车 => enter
     > * 删除 => delete (捕获“删除”和“退格”键)
     > * 退出 => esc
     > * 空格 => space
     > * 换行 => tab (特殊，必须配合keydown去使用)
     > * 上 => up
     > * 下 => down
     > * 左 => left
     > * 右 => right
     >
     >   可以通过全局 `config.keyCodes` 对象自定义按键修饰符别名：
     > * Vue.config.keyCodes.f1 = 112
     >
* v-bind修饰符
  1. sync

     > 能对props进行一个双向绑定
     >

     ```html
     //父组件
     <comp :myMessage.sync="bar"></comp> 
     //子组件
     this.$emit('update:myMessage',params);


     相当于
     //父亲组件
     <comp :myMessage="bar" @update:myMessage="func"></comp>
     func(e){
      this.bar = e;
     }
     //子组件js
     func2(){
       this.$emit('update:myMessage',params);
     }

     ```
  2. prop

     > 设置自定义标签属性，避免属性暴露在标签上，防止污染HTML结构
     >
  3. camel

     > 由于HTML 特性是不区分大小写的。
     >
     > `<svg :viewBox="viewBox"></svg>`
     > 这将导致渲染失败，因为 SVG 标签只认 viewBox，却不知道 viewbox 是什么。
     > 如果我们使用.camel修饰符，那它就会被渲染为驼峰名。
     > 另，如果你使用字符串模版，则没有这些限制。
     >


[上一篇](https://hyramxue.github.io/post/zai-created-he-mounted-qu-qing-qiu-shu-ju-%EF%BC%8C-you-shen-me-qu-bie-%EF%BC%9F.html)