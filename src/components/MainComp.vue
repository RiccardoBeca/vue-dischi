<template>
  <div class="bg-container">
     <div class="container d-flex flex-wrap pt-5">
     <CardComp
     v-for="(disc, index) in discsArray" :key="`disc${index}`"
     :cardItem="disc"
     />
    </div>
  </div>
 
  
</template>

<script>
import axios from "axios";
import CardComp from './CardComp.vue';
export default {
  name: "MainComp",
  components: { CardComp },
  data(){
    return{
      urlApi: "https://flynn.boolean.careers/exercises/api/array/music",
      discsArray: [],
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