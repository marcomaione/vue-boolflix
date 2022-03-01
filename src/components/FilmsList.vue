<template>
  <div class="card">
    <MyCard v-for="(film, index) in films" :key="index" :info='film'></MyCard>
  </div>


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

<style lang="scss">

</style>