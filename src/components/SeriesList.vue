<template>
    <div>
      <h1>Elenco serie tv</h1>
      <MyCard v-for="(serie, index) in series" :key="index" :info='serie'></MyCard>
    </div>
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