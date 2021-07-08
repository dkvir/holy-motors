<template>
  <router-view />
</template>

<script>


export default {
  name: 'App',
  components: {
    
  }
}
</script>

<style lang="scss">
@import '@/assets/scss/main.scss';

#app {
  width: 100%;
  height: 100%;
  overflow: hidden;
  font-family: $Helvetica_normal, $Helvetica_it,
  $Helvetica_roman, $Helvetica_it_56, $Helvetica_bold, $Helvetica_it_bold;

}
</style>
