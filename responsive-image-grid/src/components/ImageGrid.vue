<template>
  <div>
    <h1>Images</h1>
    <div class="image-grid-container">
      <div v-for="image,i in imageList" :key="i">
        <ImageCard 
          :url='image.urls.regular' 
          :imageUrl='image.links.html'
          :userProfileLink='image.user.links.html'
          :userName='image.user.first_name'
        />
      </div>
    </div>
    
    </div>

</template>

<script>
import ImageCard from './ImageCard.vue'

export default {
  name: 'ImageGrid',
  components: {
    ImageCard
  },
  data(){
    return {
      imageList:[],
    }
  },
  mounted(){this.getImages()},
  methods:{
    getImages(){
      const getUrl='https://api.unsplash.com/photos/?client_id=iSUqmKX0n0RdggjIvapCQ39F9Pdq_DGzEL8C3YmOERA'
      const axios = require('axios').default;
      axios({url: getUrl, 
          method: "GET",
          headers: {
              "Content-type": "application/json;charset=UTF-8",
              'Accept': 'application/json' ,
              'X-Requested-With': 'XMLHttpRequest',
          }
      })
      .then(response =>{ 
        this.imageList=this.imageList.concat(response.data);
      })
      .catch(err => console.log(err));
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
