<template>
  <ul>
    <Mycard v-for="(serie, index) in series" :key="index" :info='serie'></Mycard>
  </ul>
</template>

<script>

import MyCard from './partials/MyCard.vue';

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