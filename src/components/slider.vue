<template>
  <mt-swipe :auto="4000" style="height: 25rem">
    <mt-swipe-item v-for="imgItem in titleList" class="mint-swipe-item">
      <img :src="imgItem.img" alt="">
      <div style="position: absolute;top:230px;font-size: 20px;left:25px;color: #fff">{{imgItem.title}}</div>
    </mt-swipe-item>
  </mt-swipe>
</template>

<script>
  export default {
    data () {
      return {
        titleList:[

        ],
      }
    },
    created(){
      this.findDaily();
    },
    methods: {
      findDaily(){
        this.api.findDaily({},(d)=>{
          var newary=d.slice(0, 5);
          for (var value of newary) {
            var jsonData={
              img:"http://localhost:3000/"+value.fliename,
              title:value.title
            }
            this.titleList.push(jsonData);
//            this.titleList.push(value.title);
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
