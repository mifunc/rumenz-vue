<template>
  <div>
     name:{{name}}
     <br/>
     type:{{type}}
     <br/>
     list:{{list}}
     <br/>
     isView:{{isView}}
     <br/>
     <button @click="handClick">change</button>
  </div>
</template>

<script>
export default {
    //子组件的名称
    name:"Props",
    props:{
        name:String,
        type:{
            validator:function(val){
                return ["入门","小站","Rumenz"].includes(val)
            }
        },
        list:{
            type:Array,
            default:()=>[]
        },
        isView:{
            type:Boolean,
            default:false
        },
        onChange:{
            type:Function,
            default:()=>{}
        }
    },
    methods:{
        handClick(){
            this.onChange(this.type==="入门"?"one":"tow")
        }
    }

}
</script>

<style>

</style>