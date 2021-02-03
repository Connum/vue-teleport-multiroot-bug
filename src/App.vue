<template>
    <MyLib :children="children" /> which <code>&lt;teleport&gt;</code>s single-root components (green) and multi-root components (red) to the body
    <p><button @click="removeLastChild">delete last child of each</button> => see how the single-root components are removed, but the multi-root components remain, despite the parent being removed:</p>
    {{ children }}
</template>

<script>
  import { reactive } from 'vue'
  import MyLib from '/lib/MyLib.js'

  export default {
    components: { MyLib: MyLib.Component },
    setup() {
      const children = reactive(['single', 'multi', 'single', 'multi', 'single', 'multi', 'single'])

      const removeLastChild = (data) => {
        children.pop()
      }
      
      return {
        children,
        removeLastChild
      }
    }  
  }
</script>

<style>
  p {
    font-family: sans-serif
  }
</style>
