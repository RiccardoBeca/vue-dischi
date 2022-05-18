<template>

   <select 
   @change="$emit('scegliGenere', cambiaGenere)"
   name="" id="">
    <option value="">Seleziona un genere</option>
    <option value="">Jazz</option>
    <option value="">Rock</option>
    <option value="">Pop</option>
  </select>
</template>

<script>
export default {
  name: "SelectComp",
  data(){
    return {
      cambiaGenere:""
    }
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/_vars.scss';
@import '../assets/style/_general.scss';
@import '../assets/style/_utils.scss';

</style>