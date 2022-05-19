<template>
<div class="container-bg d-flex justify-content-center align-items-center">
  <div class="container-fluid d-flex justify-content-between">
  <div class="logo">
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 167.5 167.5" class="spotify-logo"><title>Spotify</title><path fill="rgb(49, 189, 90)" d="M83.7 0C37.5 0 0 37.5 0 83.7c0 46.3 37.5 83.7 83.7 83.7 46.3 0 83.7-37.5 83.7-83.7S130 0 83.7 0zM122 120.8c-1.4 2.5-4.6 3.2-7 1.7-19.8-12-44.5-14.7-73.7-8-2.8.5-5.6-1.2-6.2-4-.2-2.8 1.5-5.6 4-6.2 32-7.3 59.6-4.2 81.6 9.3 2.6 1.5 3.4 4.7 1.8 7.2zM132.5 98c-2 3-6 4-9 2.2-22.5-14-56.8-18-83.4-9.8-3.2 1-7-1-8-4.3s1-7 4.6-8c30.4-9 68.2-4.5 94 11 3 2 4 6 2 9zm1-23.8c-27-16-71.6-17.5-97.4-9.7-4 1.3-8.2-1-9.5-5.2-1.3-4 1-8.5 5.2-9.8 29.6-9 78.8-7.2 109.8 11.2 3.7 2.2 5 7 2.7 10.7-2 3.8-7 5-10.6 2.8z"/></svg>
  </div>
   <select 
   v-model="genereSelezionato"
   @change="changeValue"
   name="" id="">
    <option value="">Seleziona un genere</option>
    <option value="Jazz">Jazz</option>
    <option value="Rock">Rock</option>
    <option value="Pop">Pop</option>
  </select>
</div>
</div>

  
</template>

<script>
export default {
    name: "HeaderComp",
    data(){
    return {
      genereSelezionato:"",
    }
  },

  methods:{
    changeValue(){
      this.$emit("cambiaValore", this.genereSelezionato);
    },
   
  },
  
  
 
}
</script>

<style lang="scss" scoped>
@import '../assets/style/_vars.scss';
@import '../assets/style/_general.scss';
@import '../assets/style/_utils.scss';

.container-bg{
  background-color: rgb(45, 57, 69);
  height: 80px;
}
.logo{
  width: 50px;
}

</style>