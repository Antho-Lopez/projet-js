<template>
  <div v-if="getSouhait.souhait">
    <detail
    :pays = getSouhait.souhait.pays
    :ville = getSouhait.souhait.ville
    :description = getSouhait.souhait.description
    :nb_personne = getSouhait.souhait.nb_person
    :image = getSouhait.souhait.image
    :prix = getSouhait.souhait.prix
    :date_debut = getSouhait.souhait.date_debut
    :date_fin =  getSouhait.souhait.date_fin
    :nb_person =  getSouhait.souhait.nb_person
    :update = update
    :id = id
    ></detail>
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
    this.showSouhait({id: this.id})
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
    //   this.$router.push({ name: 'souhait', params: { formulaire : formulaire, id: id, image: image }});
    // },
    ...mapActions('souhaits', ['showSouhait'])

  }, 
  computed:{
    ...mapGetters('souhaits', ['getSouhait'])
  } 
  };
</script>
<style>
  
</style>