<template>
  <mt-swipe :auto="4000" style="height: 25rem">
    <mt-swipe-item v-for="imgItem in imgList" class="mint-swipe-item">
      <img :src="imgItem" alt="">
    </mt-swipe-item>
  </mt-swipe>
</template>

<script>
  export default {
    data () {
      return {
        imgList:[]
      }
    },
    created(){
      this.findDaily();
    },
    methods: {
      findDaily(){
        this.api.findDaily({},(d)=>{
          var newary=d.slice(0, 3);
          for (var value of newary) {
            this.imgList.push(value.imgTit);
          }
        })
      }
    },
  }
</script>
<style>
  .mint-swipe-item img{
    width: 100%;
    height: 100%;
  }
</style>
