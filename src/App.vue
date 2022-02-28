<template>
  <div id="app">
    <MyHeader @search="getFilms"></MyHeader>
    <MyMain></MyMain>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import MyMain from './components/MyMain.vue'

const axios = require('axios');

export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain,
  },
  data() {
    return {
      films: []

    }

  },
  methods: {
    getFilms(keyWord) {
      console.log(keyWord);
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=431bdbe406cda6cf376d9ec554586227&query=' + keyWord +'')
      .then((response) => {
        this.films = response.data.results;
        console.log(response);

      })
    }
  }
}
</script>

<style lang="scss">



</style>
