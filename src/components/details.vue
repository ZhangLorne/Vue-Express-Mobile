<template>
 <div class="list-cont">
   <ul>
     <h2 class="title">今日热闻</h2>
     <li v-for="items in newsList" class="detail-box">
       <div class="detail-box-title">
         <p>
           {{items.title}}
         </p>
       </div>
       <div class="detail-box-img">
         <img :src="'http://localhost:3000/'+items.fliename" alt="">
       </div>
     </li>
   </ul>
 </div>
</template>

<script>
    export default {
        data() {
            return {
              newsList:[]

            }
        },
        created(){
          this.findDaily();
        },
        methods: {
          findDaily(){
            this.api.findDaily({},(d)=>{
              this.newsList=d.reverse()
            })
          }
        },
    }
</script>
<style>
  .detail-box .detail-box-title {
    margin-right: 1rem;
    -webkit-box-flex: 1;
    -webkit-flex: 1;
    flex: 1;
  }
  .detail-box .detail-box-title p{
    font-size: 1.6rem;
    color: #4f4f4f;
  }
  .list-cont{
    padding: .5rem .5rem 0;
    background: #f2f2f2;
  }
  .title {
    color: #76787e;
    margin-left: .4rem;
    margin-bottom: .32rem;
    font-size: 1.5rem;
    font-weight: 500;
  }
  .detail-box{
    position: relative;
    min-height: 1rem;
    width: 100%;
    margin: 0.6rem auto 0;
    background: #fff;
    padding: 1rem;
    display: -webkit-box;
    display: -webkit-flex;
    display: flex;
    -webkit-box-orient: horizontal;
    -webkit-box-direction: normal;
    -webkit-flex-direction: row;
    flex-direction: row;
    border-radius:  0.5rem;
    border: 0.1rem solid #eaeaea;
    border-bottom:  0.1rem solid #d0d0d0;
  }
  .detail-box .detail-box-img>img{
    width: 8rem;
    height: 6.5rem;
  }
</style>
