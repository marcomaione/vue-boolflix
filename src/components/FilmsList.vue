<template>
  <ul>
    <MyCard v-for="(film, index) in films" :key="index" :info='film'></MyCard>
  </ul>


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