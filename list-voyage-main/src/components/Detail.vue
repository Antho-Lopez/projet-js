<template>

  <!-- <div class="card">
    <img :src="image" alt="">
    <div class=card-right>
      
      <h2>{{ pays }}</h2>
      <span>{{ ville }}</span>
      <p>{{ description }}</p>
      <span>{{ prix }}</span>
      <span>{{ nb_person }}</span>

      <formulaire :id = id
      :date_debut = date_debut
      :date_fin = date_fin
      :nb_person = nb_person></formulaire>
    </div>

  </div> -->

  <div class="home-pic">
    <img class="home-p" :src="image">
  </div>
  <div class="presentation-text">
    <h2 class="">{{ pays }}</h2>
    <p>{{ description }}</p>
  </div>
  <h2 class="h2">Choisir cette destination</h2>
  <div id="formulaire" class="custom-form">
    <!-- <form @submit.prevent>
    <div class="form">
      <div class="left">
        <div class="top-left">
          <div class="input-date">
            <label for="start">Date d'arrivée</label>
            <input  v-model.trim="start" type="date" id="start" name="start">
          </div>
          <div class="input-date">
            <label for="end">Date de départ</label>
            <input v-model.trim="end" type="date" id="end" name="end">
          </div>
        </div>
        <div class="input-date">
          <label class="top-marg">Nombre de personnes</label>
          <input type="text">
        </div>
      </div>
      <div class="vertical">
        <p> </p>
      </div>
      <div class="right">
        <p>à partir de <br><span class="big-text">1028€</span>/personnes</p>
        <p>Le gerant peut appliquer des frais supplémentaires</p>
        <button type="submit" @click="addDestination(id)">Réserver</button>
      </div>
    </div>
    </form> -->

     <formulaire :id = id
      :date_debut = date_debut
      :date_fin = date_fin
      :nb_person = nb_person
      :update= update></formulaire>
    
  </div>
</template>
<script>
// import { mapActions, mapGetters } from 'vuex';
import Formulaire from './Formulaire.vue';

export default {
  // mounted() {
  //   if(this.date_debut && this.date_fin) {
  //     console.log('destination detail')
  //     this.showSouhait({id: this.id})

  //   } else {
  //     console.log(this.id);
  //     const id = this.id;
  //     this.showDestination({id})
  //   }
  // },
  components:{
    Formulaire
  },
  props: { 
    id: String, 
    date_debut: String, 
    date_fin: String, 
    update: Boolean,
    pays: String,
    prix: String, 
    image: String, 
    ville: String, 
    nb_person: String, 
    description: String,
  }, 
  methods: {
    // goToForm(id, formulaire, image) {
    //   this.$router.push({ name: 'destination', params: { formulaire : formulaire, id: id, image: image }});
    // },
    // ...mapActions('destinations', ['showDestination']),
    // ...mapActions('souhaits', ['showSouhait'])

  }, 
  computed:{
    // ...mapGetters('destinations', ['getDestination'])
  } 
  };
</script>

<style scoped>

   .home-pic{
    width: 80vw;
    margin-left: 10vw;
    margin-top: -1px;
  }

 .presentation-text{
    width: 80vw;
    margin-left: 10vw;
    font-family: 'Roboto';
    margin-top: 50px;
    color: #292929;
  }

  .presentation-text h2{
    font-size: 36px;
    font-weight: bold;
  }

  .h2{
    font-size: 36px;
    font-weight: bold;
    width: 80vw;
    margin-left: 10vw;
    margin-top: 10vh;
  }

  .presentation-text p{
    font-size: 20px;
    margin-top: -20px;
    width: 70%;
  }
  .home-p{
    width: 80vw;
  }
  .vertical{
    height: 250px;
    width: 2px;
    border-right: 1px solid #bbbbbb;
  }
  .custom-form{
    margin-top: 5vh;
    margin-bottom: 5vh;
    border: 1px solid #BBBBBB;
    border-radius: 5px;
    width: 80vw;
    padding-top: 25px;
    padding-bottom: 25px;
    margin-left: 10vw;
  }

  .form{
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-items: center;
    height: 100%;
  }

  .left{
    display: flex;
    flex-direction: column;
  }

  .top-left{
    display: flex;
    flex-direction: row;
  }

  .input-date{
    display: flex;
    flex-direction: column;
    padding-left: 10px;
    padding-right: 10px;
  }

  label{
    padding-bottom: 10px;
  }

  input{
    background-color: rgb(223, 235, 240);
    padding: 10px;
    border: none;
  }

  .top-marg{
    margin-top: 25px;
  }
  .big-text{
      font-size: 40px;
      font-weight: bold;
  }

  button{
    margin-top: 3vh;
    width: 100%;
    background-color: #F2B203;
    padding: 14px;
    border: 0px;
    border-radius: 14px;
    font-size: 20px;
    font-weight: bold;
    cursor: pointer;
  }

  button:hover{
     background-color: #d69e04;
  }

  

</style>