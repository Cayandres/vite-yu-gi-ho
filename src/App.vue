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
      axios.get(store.apiUrl)
        .then(result => {
          store.characterList = result.data.data;
          store.isLoading = false;
        })
    }
  },

  mounted(){
    this.getApi()

  }

}
</script>

<template>

  <Loader v-if="store.isLoading"/>
 
  <div v-else>
   <Header
  title="Yu-GI-Ho Api"/>

  <Main/>  
  </div>
 

</template>

<style lang="scss">
@use './scss/main.scss';


</style>
