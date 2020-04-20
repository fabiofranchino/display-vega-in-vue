<template>
  <div id="app">
    <UI v-if="!url" :url.sync="url" />
    <Display v-if="url" :url="url" />
  </div>
</template>




<script>
import UI from './components/UI.vue'
import Display from './components/Display.vue'

export default {
  components: {
    UI, Display
  },
  data(){
    return{
      url:''
    }
  }
}
</script>



<style src="../node_modules/milligram/dist/milligram.css"></style>
<style>
*{
  box-sizing: border-box;
}
html, body, #app{
  width: 100%;
  height: 100%;
  overflow: hidden;
  padding: 0;
  margin: ;
}
#app {
  display: flex;
  
}
</style>
