<template>
  <div id="app">
    <MyHeader></MyHeader>
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
  methods: {
    getFilm() {
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=431bdbe406cda6cf376d9ec554586227&query=star Wars')
      .then((response) => {
        this.MyMain = response.data.response;

      })
    }
  }
}
</script>

<style lang="scss">

</style>
