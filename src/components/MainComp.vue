<template>
  <div>
      <HeaderComp @cambiaValore= 'genereScelto'/>
      <div class="bg-container">
        <div class="container d-flex flex-wrap pt-5">
        <CardComp
        v-for="(disc, index) in discFiltered" :key="`disc${index}`"
        :cardItem="disc"
        />
        </div>
      </div>
  </div>
  
 
  
</template>

<script>
import axios from "axios";
import CardComp from './CardComp.vue';
import HeaderComp from "./HeaderComp.vue";

export default {
  name: "MainComp",
  components: { CardComp, HeaderComp },
  data(){
    return{
      urlApi: "https://flynn.boolean.careers/exercises/api/array/music",
      discsArray: [],
      genereSelezionato: "",
    }
  },

  mounted(){
    this.getApi()
    console.log(this.discsArray);
  },

  methods:{
    getApi(){
      axios.get(this.urlApi)
      .then(r=>{
        this.discsArray = r.data.response;
        console.log(r.data);
      })
    },
    genereScelto(cambiaGenere){
      this.genereSelezionato = cambiaGenere;
      console.log(this.genereSelezionato);
    },
     
  },

  computed: {

    discFiltered(){
        console.log(`ciao`,this.genereSelezionato);
      if(this.genereSelezionato === ""){
        console.log(`ciao`,this.discsArray);
        return this.discsArray;
      }

      return this.discsArray.filter(disc => this.genereSelezionato === disc.genre)

    }
    
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/_vars.scss';
@import '../assets/style/_general.scss';
@import '../assets/style/_utils.scss';

.bg-container{
  min-height: 100vh;
  background-color: rgb(29, 44, 58);
}

</style>