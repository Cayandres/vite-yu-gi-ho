
<script>

export default {
  name: 'Header',
  props:{
    title: String,
  }
}
</script>

<template>
  <div class="container-100">
    <img src="../assets/71-713842_transparent-yugioh-logo-yu-gi-oh-the-art.jpg" alt="">
    <h1>{{ title }}</h1>
  </div>
</template>

<style lang="scss" scoped>
@use '../scss/partials/vars' as*;
.container-100{
  display: flex;
  align-items:  center;
  width: 100%;
  height: 80px;
  background-color: $secondary-color;
  img{
    height: 100%;
    
  }
  h1{
    display: inline-block;
    font-size: 50px;
  }

}

</style>