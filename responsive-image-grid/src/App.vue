<template>
  <div id="app">
    <div style="display:flex">
      <h1 class="images-title active">IMAGES 
        <span style='font-weight:300;font-size:24px;'>(variable sizes)</span>
      </h1>
      <h1 class="image-galery-title">GALERY
        <span style='font-weight:300;font-size:24px;'>(same size images)</span>
      </h1>
    </div>
    <ImageGrid/>
    <ImageGalery/>
  </div>
</template>

<script>
import ImageGrid from './components/ImageGrid.vue'
import ImageGalery from './components/ImageGalery.vue'

export default {
  name: 'App',
  components: {
    ImageGrid,
    ImageGalery
  },
  mounted(){
    const imagesTitle=document.querySelector(".images-title")
    const imageGaleryTitle=document.querySelector(".image-galery-title")
    const differentSizeGalery=document.querySelector(".image-grid-container")
    const sameSizeGalery=document.querySelector(".galery-grid-container")
    imagesTitle.addEventListener("click", function() {
      imagesTitle.classList.add('active')
      imageGaleryTitle.classList.remove('active')
      differentSizeGalery.style.display='grid'
      sameSizeGalery.style.display='none'
    });
    imageGaleryTitle.addEventListener("click", function() {
      imageGaleryTitle.classList.add('active')
      imagesTitle.classList.remove('active')
      differentSizeGalery.style.display='none'
      sameSizeGalery.style.display='flex'
    });
  }
}
</script>

<style lang="scss">
  @import './assets/style.scss';
  @import url('https://fonts.googleapis.com/css2?family=Lato:ital@1&display=swap');
</style>

