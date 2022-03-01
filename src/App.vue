<template>
  <div id="app">
    <MyHeader @search="getFilms"></MyHeader>
    <MyMain :films="films" :series="series"></MyMain>
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
      series: [],
      api_key: '431bdbe406cda6cf376d9ec554586227',
      language: 'it-IT'
    }
  },
  methods: {
    dosearch(keyWord) {
      this.getFilms(keyWord);
      this.getTv(keyWord);

    },

    // faccio una chiamata per i film
    getFilms(keyWord) {
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=' + this.api_key + '&query=' + keyWord + '&language' + this.language)
      .then((response) => {
        this.films = response.data.results;
      })
    },

    // faccio una chiamata per le serie tv
    getTv(keyWord) {
      axios.get('https://api.themoviedb.org/3/search/tv?api_key=' + this.api_key + '&query=' + keyWord + '&language' + this.language)
      .then((response) => {
        this.series = response.data.results;
      })
    }
  }
}
</script>

<style lang="scss">



</style>
