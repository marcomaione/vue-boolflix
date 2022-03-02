<template>
    <div class="cardFilm">
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
.cardFilm {
  width: 90%;
  margin: 0px auto;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  
}


</style>