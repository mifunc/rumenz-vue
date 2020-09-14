<template>
  <div>
      <!--具名插槽-->
      <slot name="title"/>
      <!--作用域插槽 向父组件传递值-->
      <slot name="item" v-bind="{value:'vue'}" />
  </div>
</template>

<script>
export default {
    name:"test"
}
</script>

<style>

</style>