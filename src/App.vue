<template>

<div>
  <HeaderComp/>
  <MainComp/>
</div>

 
</template>

<script>
import axios from "axios";
import HeaderComp from "./components/HeaderComp.vue";
import MainComp from "./components/MainComp.vue";

export default {
  name: 'App',

  data(){
    return{
      urlApi: "https://flynn.boolean.careers/exercises/api/array/music",
      discsArray: [],
    }
  },

  components: {
    HeaderComp,
    MainComp
  },

  mounted(){
    this.getApi()
  },

  methods:{
    getApi(){
      axios.get(this.urlApi)
      .then(r=>{
        this.discsArray = r.data;
        console.log(r.data);
      })
    }
  }
}
</script>

<style lang="scss">

</style>
