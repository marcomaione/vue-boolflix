<template>
  <div id="app">
    <MyHeader @search="getFilms"></MyHeader>
    <MyMain :films="films"></MyMain>
    <FilmsList></FilmsList>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import MyMain from './components/MyMain.vue'
import FilmsList from './components/FilmsList.vue'

const axios = require('axios');

export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain,
    FilmsList,
  },
  data() {
    return {
      films: [],
      api_key: '431bdbe406cda6cf376d9ec554586227',
      language: 'it-IT'

    }

  },
  methods: {
    getFilms(keyWord) {
      console.log(keyWord);
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=' + this.api_key + '&query=' + keyWord + '&language' + this.language)
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
