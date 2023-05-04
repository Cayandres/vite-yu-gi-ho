
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
.counter{
  text-align: center;
  background-color: black;
  padding: 30px;
  margin-bottom: 20px;
  color: white;
 }
</style>