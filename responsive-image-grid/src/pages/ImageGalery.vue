<template>
  <div>
    <div class="galery-grid-container">
  
        <ImageCard v-for="image,i in imagesList" :key="i"
            :url='image.urls.regular' 
            :imageUrl='image.links.html'
            :userProfileLink='image.user.links.html'
            :userName='image.user.first_name'
        />
 
    </div>
    
    </div>

</template>

<script>
import ImageCard from '../components/ImageCard.vue'

export default {
  name: 'ImageGalery',
  components: {
    ImageCard
  },
  data(){
    return {
      imagesList:[],
    }
  },
  mounted(){this.getImages()},
  methods:{
    getImages(){
      const axios = require('axios').default;
      let pageCount=3;

      do{
        let getUrl='https://api.unsplash.com/photos?page='+pageCount+'&client_id=iSUqmKX0n0RdggjIvapCQ39F9Pdq_DGzEL8C3YmOERA'
        
        axios({url: getUrl, 
            method: "GET",
            headers: {
                "Content-type": "application/json;charset=UTF-8",
                'Accept': 'application/json' ,
                'X-Requested-With': 'XMLHttpRequest',
            }
        })
        .then(response =>{
            response.data.forEach(image => {
                this.imagesList.push(image);
            });
            
        })
        .catch(err =>{ console.log(err); return;});
        pageCount--;

      } while(pageCount>0)
    },
  },
}
</script>

