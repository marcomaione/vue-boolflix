<template>
<section>
  <h1>Elenco film</h1>
  <ul>
    <MyCard v-for="(film, index) in films" :key="index" :info='film'></MyCard>
  </ul>
</section>

</template>

<script>

import MyCard from './partials/MyCard.vue';

export default {
    name:"FilmsList",
    props: {
        'films': Array
    },
    components: {
      MyCard

    }

}
</script>

<style>

</style>