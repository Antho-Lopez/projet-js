<template>
  <div class="card">
    <img :src="image" alt="" @click="goToForm(id)">
    <h2>{{ pays }},<br> {{ ville }}</h2> 
  </div>
</template>
<script>
  
  import { mapActions } from 'vuex';
  
  export default {
    mounted(){
        this.getDestinationsBdd()
      },
    props: {
      image: String, 
      description: String, 
      prix: Number, 
      id: String, 
      ville: String, 
      pays: String, 
    }, 

    methods: {
      goToForm(id) { 
        this.$router.push({ name: 'destination_detail', params: { id: id, }});
      }, 

      ...mapActions('destinations', ['getDestinationsBdd'])
    }
  };

</script>
<style>

  body{
    margin: 0; 
    padding: 0;
    font-family: 'roboto';
    color: #292929;
  }

  .card{
    margin-right: 1vw;
    margin-bottom: 40px;
  }

  .card img{
    width: 16vw;
    height: 16vw;
    cursor: pointer;
    
  }

  .card h2{
    margin-top: -90px;
    padding-left: 10px;
    color: white;
    font-family: 'Roboto';
    font-weight: bold;
    text-transform: capitalize;
    font-size: 28px;
  }

</style>