<template>
  <div id="app">
    <Images/>
    <ImageGalery/>
  </div>
</template>

<script>
import Images from './components/Images.vue'
import ImageGalery from './pages/ImageGalery.vue'

export default {
  name: 'App',
  components: {
    Images,
    ImageGalery
  }
}
</script>

<style lang="scss">
  @import './assets/style.scss';
  @import url('https://fonts.googleapis.com/css2?family=Lato:ital@1&display=swap');
</style>

