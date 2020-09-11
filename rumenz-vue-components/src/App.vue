<template>
<div id="app">
   {{msg}}
    <div>
        <!--v-model绑定到info变量上-->
        <input type="text" v-model="info">
        <!--@click绑定点击事件-->
        <button @click="handle">添加</button>
    </div>
    <!--必须绑定:key :item表示组件ItemOne.vue的定义的变量,通过的属性的方式传递值到子组件-->
    <item-one v-for="item in list" :key="item" :item="item"></item-one>
</div>
</template>

<script>
import ItemOne from './components/ItemOne'

export default {
  name: 'App',
  data() {
        return {
            msg: "hello 入门小站",
            info: '',
            list: []
        }
    },
    methods: {
        handle(){
            this.list.push(this.info);
            this.info='';
        }
    },
  components: {
    ItemOne
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
