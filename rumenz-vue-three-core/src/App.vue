<template>
<div id="app">
   {{msg}}
   <!--属性绑定格式 :[自组件的属性]:[父组件的属性]-->
   <Props 
   :name="name"
   :type="type"
   :list="list"
   :isView="view"
   :onChange="onChange"
   />
   <Event
     @change="onChangeVal"
     :name="name"
   />
   <Solt>
      <template v-slot:title>
         <h1>这段内容会填充到子组件中</h1>
      </template>
      <!--使用props来接收{value:'vue'}值-->
      <template v-slot:item="props">
          <p>======={{props}}</p>
      </template>
   </Solt>
  
</div>
</template>

<script>
import Props from './components/Props'
import Event from './components/Event'
import Solt from './components/Solt'
export default {
  name: 'App',
  data() {
        return {
            msg: "hello 入门小站",
            name:"name",
            type:"入门",
            list:['入门','小站'],
            view:true
        }
    },
    methods: {
      onChange(val){
        this.name=val;
      },
      onChangeVal(val){
        this.name=val;
      }

       
    },
  components: {
    Props,
    Event,
    Solt
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
