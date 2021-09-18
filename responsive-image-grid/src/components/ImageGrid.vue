<template>
  <div>Images</div>
</template>

<script>
export default {
  name: 'ImageGrid',
  props: {
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
        console.log(response)
      })
      .catch(err => console.log(err));
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
