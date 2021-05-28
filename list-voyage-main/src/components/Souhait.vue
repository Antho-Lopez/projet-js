<template>
  <div class="card">
    <img :src="image" alt="">
    <div class="text-card">
      <div class="text-left">
        <h2>{{ pays }}, {{ ville }}</h2>
        <p>Du {{ date_debut }} au {{ date_fin }}</p>
        <p class="p-marg">Pour {{nb_person}} personnes</p>   
      </div>
      <div class="text-right">
        <p>à partir de <br><span class="big-text">1028€</span>/personnes</p>
        <button class="delete-btn" @click="deleteSouhait(id)">Supprimer</button>
        <button class="update-btn" @click="updateSouhait(id, date_debut, date_fin)">Modifier</button>
      </div>
    </div>
  </div>
</template>
<script>
import { mapActions } from 'vuex';
  // import Name from '@/components/Name.vue';
  
  export default {

    mounted(){
      this.getDestinationsSouhaitBdd()
    },
    props: {
      id: String, 
      image: String,
      ville: String, 
      pays: String, 
      description: String, 
      prix: Number, 
      date_debut: String, 
      date_fin: String,
      nb_person: String,
    }, 
    methods: {
      deleteSouhait(id) {
        this.deleteSouhait({id: id}); 

      }, 

      updateSouhait(id, date_debut, date_fin) {
        this.$router.push({ name: 'souhait_detail', params: { id: id, date_debut: date_debut, date_fin: date_fin, update: true }});
      }, 

      ...mapActions('souhaits', ['deleteSouhait', 'getDestinationsSouhaitBdd'])
    }
  };
</script>
<style scoped>
    
    .card{
      width: 100%;
      height: 300px;
      overflow: hidden;
      margin-top: 10px;
      margin-bottom: 0px;
      display: flex;
      flex-direction: column;
      color: white;
    }

    .card img{
      width: 100%;
      height: 700px;
    }

    .card h2{
      margin: 0px;
      padding-left:0px;
    }

    .p-marg{
      margin-top: -15px;
    }

    .text-card{
      margin-top: -600px;
      display: flex;
      font-weight: bold;
      justify-content: space-between;
      align-items: center;
      width: 96%;
      margin-left: 2%;
    }

    .big-text{
      font-size: 40px;
    }

    .text-right{
      display: flex;
      flex-direction: column;

    }

    .text-right button{
      margin-bottom: 10px;
      padding: 7px;
      border: none;
      border-radius: 4px;
      color: white;
      font-weight: bold;
      cursor: pointer;
    }
    
    .delete-btn{
      background-color: rgb(226, 36, 36);
    }

    .delete-btn:hover{
      background-color: rgb(199, 33, 33);
    }

    .update-btn{
      background-color: #F2B203;
    }

    .update-btn:hover{
      background-color: #d19b04;
    }

</style>