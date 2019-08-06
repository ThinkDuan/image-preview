<template>
  <div class="preview" :style="{width: realWidth,height:realHeight}">
    <img v-for="(item,index) in realImageList" :key="index" :src="item.src" :alt="item.alt" :title="item.title">
  </div>
</template>

<script>
export default {
  name: 'ImagePreview',
  props: {
    imageList: {
      type: Array,
      default: function(){
        return []
      }
    },
    imagesRef: {
      
    },
    width: {
      type: Number,
      default: 600
    },
    height: {
      type: Number,
      default:  600
    }
  },
  computed: {
    realWidth(){
      return this.width + 'px'
    },
    realHeight(){
      return this.height + 'px'
    },
    realImageList(){
      if(this.imageList && this.imageList.length > 0){
        return this.imageList;
      } else {
        return []
      }
    },
    realRef(){
      console.log('imagesRef',this.imagesRef);
      return this.imagesRef;
    }
  },
  watch: {
    realRef(val){
      console.log(val);
    }
  }
}
</script>
<style scoped>
.preview{
  position: fixed;
  right: 0;
  bottom: 0;
}
</style>
