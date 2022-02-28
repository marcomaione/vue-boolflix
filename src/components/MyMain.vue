<template>
  <div class="container">
    <FilmsList :films='films'></FilmsList>

  </div>
</template>

<script>
  import FilmsList from './FilmsList.vue'

  export default {
  
  name:"MyMain",
  props: {
   'films': Array
  },
  components: { 
    FilmsList 
  }
}
</script>

<style lang="scss">
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
.container {
    background-color:#434343;
    width: 100%;
    min-height: calc(100vh - 80px);
    display: flex;
}

</style>