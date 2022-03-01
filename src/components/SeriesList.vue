<template>
    <ul>
      <h1>Elenco serie tv</h1>
      <MyCard v-for="(serie, index) in series" :key="index" :info='serie'></MyCard>
    </ul>
</template>

<script>

import MyCard from './partials/MyCard.vue'

export default {
  name:"SeriesList",
  props: {
    'series': Array
  },
  components: {
    MyCard
  }

}
</script>

<style>

</style>