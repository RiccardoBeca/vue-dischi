<template>

  <div class="card custom p-3 pb-5">
    <div class="img-container">
      <img :src="cardItem.poster" :alt="cardItem.title">
    </div>
    <div class="text-container text-center">
      <h4 class="pt-3">{{cardItem.title}}</h4>
      <h5>{{cardItem.author}}</h5>
      <h6>{{cardItem.year}}</h6>
    </div>   
  </div>

  
</template>

<script>
export default {
  name:"CardComp",
  props:{
    cardItem: Object,
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/_vars.scss';
@import '../assets/style/_general.scss';
@import '../assets/style/_utils.scss';


.custom{
  flex-basis: calc(20% - 40px);
  background-color: rgb(45, 57, 69) !important;
  margin: 20px;
}
.img-container{
  display: flex;
  align-self: center;
  // width: 100%;
  width: 100%;
  img{
    height: 100%;
    width: 100%;
  }
}

.text-container{
  h4{
    font-size: 1rem;
    color: white;
    text-transform: uppercase;
  }
  h5,h6{
    color: rgb(132, 127, 123);
  }

}

</style>