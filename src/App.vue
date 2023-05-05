<script>
import axios from 'axios'
import Header from './components/Header.vue'
import Loader from './components/partials/Loader.vue'
import Main from './components/Main.vue'
import { store } from './data/store'
export default {
  name: 'App',
  data(){
    return{
      store
    }
  },

  components:{
    Header,
    Main,
    Loader
  },
  methods:{
    getApi(){
      store.isLoading = true;
      axios.get(store.apiUrl, {
        params : {
          num: store.cardNumber,
          offset: store.cardOffset,
          type: store.searchType
        }
      })
        .then(result => {
          store.characterList = result.data.data;
          store.isLoading = false;
        })
    },

    getTypes() {
      axios.get(store.apiUrl)
      .then(result => {
        result.data.data.forEach( card => {
          if(!store.listType.includes(card.type)) store.listType.push(card.type)
        })
      })
    }
  },

  mounted(){
    this.getApi()
    this.getTypes()
  }

}
</script>

<template>
  <Header
  title="Yu-GI-Ho Api"/>

  <Loader v-if="store.isLoading"/>
  
<div v-else>
  <Main @getApi="getApi"/>  
</div>


</template>

<style lang="scss">
@use './scss/main.scss';


</style>
