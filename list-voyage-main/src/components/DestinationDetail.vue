<template>
  <div v-if="getDestination.destination">
    <detail
    :pays = getDestination.destination.pays
    :ville = getDestination.destination.ville
    :description = getDestination.destination.description
    :image = getDestination.destination.image
    :prix = getDestination.destination.prix
    ></detail>
    {{id}}
  </div>
</template>
<script>
import { mapActions, mapGetters } from 'vuex';
import Detail from './Detail.vue';
// import SouhaitDetail from './SouhaitDetail.vue';
// import Formulaire from './Formulaire.vue';


export default {
  mounted() {
    
    console.log('coucou', this.id);
    this.showDestination({id: this.id})
  },
  components:{
    // Formulaire, 
    Detail,
    // SouhaitDetail,

  },
  props: { 
    id: String, 
    date_debut: String, 
    date_fin: String, 
    update: Boolean,
  }, 
  methods: {
    // goToForm(id, formulaire, image) {
    //   this.$router.push({ name: 'destination', params: { formulaire : formulaire, id: id, image: image }});
    // },
    ...mapActions('destinations', ['showDestination']),

  }, 
  computed:{
    ...mapGetters('destinations', ['getDestination'])
  } 
  };
</script>
<style>
  
</style>