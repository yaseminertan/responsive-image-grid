<template>
  <div>
    <h1>IMAGES</h1>
    <div class="image-grid-container">
  
        <ImageRow v-for="images,i in imagesList" :key="i"
          :imageList='images' 
        />
 
    </div>
    
    </div>

</template>

<script>
import ImageRow from './ImageRow.vue'

export default {
  name: 'Images',
  components: {
    ImageRow
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
            this.imagesList.push(response.data);
        })
        .catch(err =>{ console.log(err); return;});
        pageCount--;

      } while(pageCount>0)
    },
  },
}
</script>

