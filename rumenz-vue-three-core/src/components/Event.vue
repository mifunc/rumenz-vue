<template>
    <div>
      name:{{name}}
      <input :value="name" @change="handChange"/>
      <div @click="divClick">
          <button @click="handClick">重置成功</button>
          <button @click.stop="handClick">重置成功</button>
      </div>
    </div>

</template>
<script>
export default {
    name:"Event",
    props:{
        name:String
    },
    methods:{
        divClick(){
            this.$emit("change","");
        },
        handChange(e){
            this.$emit("change",e.target.value);
        },
        handClick(){
            
        }
    }


}
</script>
<style scoped>

</style>