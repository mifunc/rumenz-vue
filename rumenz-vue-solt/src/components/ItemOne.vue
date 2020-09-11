<template>
     <li class="item">
         <input type="checkbox" v-model="checked" />
         <!--插槽的名称和下面的属性名要对应-->
          <!--插槽将checked变量传递出去,方便调用者改变变量值-->
         <slot name="comp" v-bind="{checked}"></slot>
     </li>
</template>
<script>
export default {
    //属性名应该和插槽保持一致
    props:['comp'],
    data(){
        return {
            checked:false
        }
    }
}
</script>
<!--scoped表示css样式的作用域限制在当前文件中-->
<style scoped>
.item{
   color: red;
}
</style>