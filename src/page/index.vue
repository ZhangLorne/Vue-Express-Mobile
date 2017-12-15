<template>
  <div class="hello">
    <Header></Header>
    <Slider></Slider>
    <Details></Details>
  </div>
</template>

<script>
  import Header from '../components/header.vue'
  import Slider from '../components/slider.vue'
  import Details from '../components/details.vue'
  export default {
    data () {
      return {
      }
    },
    components:{Header,Slider,Details}
  }
</script>
<style>
</style>
