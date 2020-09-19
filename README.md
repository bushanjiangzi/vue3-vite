npm install

npm run dev

npm run build

1、响应式原理浅析
reactivity文件夹
直接运行
reactivity/index.html至浏览器

2、vue3.0初试，Composition API
npm run dev

3、vite原理原理解析
node server.js

编译时的优化  Vue3最大的特点

vite ，按需加载
现代浏览器都支持es6的import了
import xx from './a.js'，浏览器会发出一个网络请求
vite拦截这个请求，去做vue相关的编译，解析等，实现了按需加载的能力
不用打包
dev秒开，build走的是rollup

<!-- 
vite原理有啥用
    1. vue3配套的工具，下一代的脚手架工具
    2. 写一个vite，完整的掌握了vue3代码编译的流程（使用层面）
        如果你想做ssr，node段解析.vue -->

1. vue2也有静态标记 ，只能标记全量的静态
    v-if内部的静态节点
    <p id="xx" style="color：red">{{name}}</p>
    这个节点，只有child是动态, vue也会全量diff
    vue3只diff children