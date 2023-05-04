
<script>
export default {
  name: 'Card',
  props:{
    img: String,
    name: String,
    type: String,
  }
}
</script>

<template>
      <div class="card">
        <img :src="img" :alt="name">
        <span class="title">{{ name }}</span>
        <span>{{ type }}</span>
      </div>  
  
</template>

<style lang="scss" scoped>
@use '../../scss/partials/vars' as*;
    .card{
      text-align: center;
      background-color: $primary-color;
      width: 18%;
      margin-bottom: 40px;
       .title{
        padding: 10px;
        font-weight: 700;
        color: white;
        height: 60px;
      }
      img{
        width: 100%;
      }
    }
</style>