<template>
  <div id="app" ref="app">
    <img src="./assets/logo.png" alt="">
    <image-preview :images-ref="appRef"></image-preview>
  </div>
</template>

<script>
import ImagePreview from './components/ImagePreview.vue'

export default {
  name: 'app',
  components: {
    ImagePreview
  },
  data(){
    return {
      appRef: ''
    }
  },
  mounted(){
    this.appRef = this.$refs.app;
  }
}
</script>