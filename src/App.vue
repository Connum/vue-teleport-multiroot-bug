<template>
    <MyLib :children="children1" /> with single-root child components (green) transported to body
    <hr>
    <MyLib :children="children2" /> with multi-root child components (red) transported to body
    <p><button @click="removeLastChild">delete last child of each</button> => see how the single-root components are removed, but the multi-root components remain</p>
</template>

<script>
  import { reactive, markRaw } from 'vue'

  import MyLib from '/lib/MyLib.js'
  import SingleRootBLock from '/lib/blocks/SingleRootBlock.vue'
  import MultiRootBLock from '/lib/blocks/MultiRootBlock.vue'

  export default {
    components: { MyLib: MyLib.Component },
    setup() {
      const children1 = reactive([markRaw(SingleRootBLock), markRaw(SingleRootBLock), markRaw(SingleRootBLock)])
      const children2 = reactive([markRaw(MultiRootBLock), markRaw(MultiRootBLock), markRaw(MultiRootBLock)])

      const removeLastChild = (data) => {
        children1.pop()
        children2.pop()
      }
      
      return {
        children1,
        children2,
        removeLastChild
      }
    }  
  }
</script>

<style>
  * {
    font-family: sans-serif
  }
</style>
