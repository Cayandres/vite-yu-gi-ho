
<script>
import { store } from '../../data/store';
export default {
  name: 'HeaderCounter',
  data(){
    return{
      store
    }
  }
}

</script>

<template>
  <div class="counter">
    <p>Carte trovate : {{store.characterList.length}}</p>
  </div>
</template>

<style lang="scss" scoped>

@use '../../scss/partials/vars' as*;
.counter{
  margin: 20px auto;
  text-align: center;
  background-color: $primary-color;
  border-radius: 10px;
  padding: 10px;
  font-weight: 600;
  color: black;
  width: 250px;
 }
</style>