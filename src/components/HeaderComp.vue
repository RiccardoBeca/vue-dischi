<template>
<div class="container-bg d-flex justify-content-center align-items-center">
  <div class="container-fluid d-flex justify-content-between">
  <div class="logo">LOGOIMG</div>
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

</style>