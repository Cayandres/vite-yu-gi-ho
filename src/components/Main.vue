<script>
  import Card from './partials/Card.vue'
  import HeaderCounter from './partials/HeaderCounter.vue'
  import { store } from '../data/store'
  export default {
    name: 'Main',
    components:{
      Card,
      HeaderCounter
    },
    data(){
      return{
        store
      }
    }
  }

</script>

<template>
  <div class="container">
    <HeaderCounter />
    <div class="cards-wrapper">
      <Card v-for="card in store.characterList" 
      :key="card.id"
      :img="card.card_images[0].image_url"
      :name="card.name"
      :type="card.archetype || card.type"/>
    </div>
  </div>
</template>


<style lang="scss" scoped>
@use '../scss/partials/vars' as*;
.container{
  margin: 40px auto;
  padding: 40px;
  background-color: $secondary-color;
  .cards-wrapper{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }
}
</style>