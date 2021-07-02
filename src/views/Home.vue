<template>
  <div class="home for-all-components">
    <homeComponent />
  </div>
  <div class="lookingfor for-all-components">looking for</div>
  <div class="about for-all-components">about</div>
  <div class="footer for-all-components">footer</div>

</template>

<script>
import homeComponent from '../components/homeComponent.vue';

export default {
  components: {
    homeComponent
  },
  setup(){

    return{
      homeComponent
    }
  }
}
</script>

<style lang="scss">
@import "../assets/scss/main.scss";
  .for-all-components{
    min-height: 100vh;
  }
  .home{
    background-color:$orange;
  }
   .lookingfor{
    background-color:aqua;
  }
  .about{
    background-color: green;
  }
  .footer{
    background-color: yellow;
  }



</style>