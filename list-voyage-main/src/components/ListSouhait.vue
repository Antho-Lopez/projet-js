<template>
    <div class="presentation-text">
      <h2 class="">Mes destinations</h2>
      <p>Voici la liste des destinations que vous avez réservé.</p>
    </div>
    <div class="list-souhait">
        <souhait class="list"
        v-for="(souhait, index) in getSouhaits" :key="index"
        :ville = souhait.ville
        :pays = souhait.pays
        :date_debut = souhait.date_debut
        :date_fin = souhait.date_fin
        :image = souhait.image
        :id = index
        :nb_person= souhait.nb_person
        ></souhait>
    </div>
</template>
<script>
import { mapGetters, mapActions } from 'vuex';
import Souhait from './Souhait.vue';

export default {
  components: { 
      Souhait 
  },

  
  mounted() {
    console.log(`souhait mount`);
    // console.log(this.$el.textContent) // Example component.
    this.getDestinationsSouhaitBdd()
  },
  computed:{
    ...mapGetters('souhaits', ['getSouhaits'])
  },
  methods:{
    ...mapActions('souhaits', ['getDestinationsSouhaitBdd'])
  }
}
</script>
<style scoped>
  
    .presentation-text{
    width: 80vw;
    margin-left: 10vw;
    font-family: 'Roboto';
    margin-top: 100px;
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

  .list-souhait{
    width: 80vw;
    margin-left: 10vw;
    margin-bottom: 10vh;
  }
</style>