<template>
  <div class="home-pic">
    <img class="home-p" src="../assets/home-pic.jpg">
  </div>
  <div class="presentation-text">
    <h2 class="">Choisir ma destination</h2>
    <p>Nous vous montrons les destinations<br> les plus populaire auprès de nos<br> utilisateurs.</p>
  </div>
  <div class="list-desti">
      <destination class="list"
        v-for="(destination, index) in getDestinations" :key="index"
        :ville = destination.ville
        :pays = destination.pays
        :image = destination.image
        :description = destination.description
        :prix = destination.prix
        :id = index
      ></destination>
  </div>
</template>
<script>
import Destination from './Destination.vue';
import { mapGetters, mapActions } from 'vuex';

export default {
    components: { 
        Destination 
    },

    mounted() {
        console.log(`At this point, vm.$el has been created and el has been replaced.`);
        // console.log(this.$el.textContent) // Example component.
        this.getDestinationsBdd()
    },
    computed:{
        ...mapGetters('destinations', ['getDestinations'])
    },
    methods:{
        ...mapActions('destinations', ['getDestinationsBdd'])
    }
}
</script>
<style scoped>

  .home-pic{
    width: 80vw;
    margin-left: 10vw;
    margin-top: -1px;
  }

  .home-p{
    width: 80vw;
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

  .presentation-text p{
    font-size: 20px;
    margin-top: -20px;
  }

  .list-desti{
    width: 80vw;
    margin-left: 10vw;
    display: flex;
    flex-direction: row;
  }
</style>