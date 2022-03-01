<template>
  <div class="container">
    <FilmsList :films='films'></FilmsList>
    <SeriesList :series='series'></SeriesList>
  </div>
</template>

<script>
  import FilmsList from './FilmsList.vue'
  import SeriesList from './SeriesList.vue'

  export default {
  
  name:"MyMain",
  props: {
   'films': Array,
   'series': Array
  },
  components: { 
    FilmsList,
    SeriesList 
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
}

</style>