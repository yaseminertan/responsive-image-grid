<template>
  <div>
    <ImageCard v-for="image,i in imageList" :key="i"
      :url='image.urls.regular' 
      :imageUrl='image.links.html'
      :userProfileLink='image.user.links.html'
      :userName='image.user.first_name'
    />
  </div>
</template>

<script>
import ImageCard from './ImageCard.vue'

export default {
  name: 'ImageRow',
  components: {
    ImageCard
  },
  props: {
    imageList: {
      type: [],
      defaault:[]
    },
  },
  
}
</script>

