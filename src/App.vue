<template>
  <h1>
    vue2.0+: 
  </h1>
  <h2>{{count}}</h2>
  <button @click="addCount">click</button>
  <h1>
    vue3.0兼容vue2.0+: 
  </h1>
  <h1>x:{{x}},y:{{y}}</h1>
  <input type="text" v-model="state.val" @keyup.enter="addTodo">
  <ul>
    <li 
      v-for="todo in state.todos" 
      :key="todo.name"
    >{{todo.name}}</li>
  </ul>
  <div>
    totoal:{{total}}
  </div>
</template>

<script>

// reactive 复杂的数据结构编程响应式
// ref是简单的数据结构
// 删除，标记已完成
import useAddTodo from './useAddTodo'
import useMouse from './useMouse'
// mixin不清晰，而且会有命名冲突的问题
export default {
  // vue2.0+写法
  data(){
    return {
      count: 1
    }
  },
  methods:{
    addCount () {
      this.count++
    }
  },
  // vue3.0写法
  setup(){
    // 这个的逻辑，很清晰 告别大几百行的组件
    let { state, total, addTodo } = useAddTodo()
    let { x, y } = useMouse()
    // 一堆useXX
    return {
      state, total, addTodo,
      x,y
    }
  }
}
// 相比于mixin好处，数据来源清晰

// 如何组合
</script>
