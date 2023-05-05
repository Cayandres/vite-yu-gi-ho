<script>
import { store } from '../../data/store';
 export default {
   name: 'Select',
   data(){
    return{
      store, 
      all:null
    }
   }
  }
</script>

<template>
  <div>
    <h5>Cerca un tipo:</h5>
    <select v-model.trim="store.searchType" @change="$emit('filter')">
      <option selected :value="all">Scegli il tipo</option>
      <option v-for="Type in store.listType"
       :key="Type"
       :value="Type">{{ Type }}</option>
    </select>
  </div>
</template>


<style lang="scss" scoped>
div{
  text-align: center;
  h5{
    display: inline-block;
    margin-right: 10px;
  }
}
</style>