<template>
    <section>
      <h1> Serie TV</h1>
      <div class="card-series">
        <MyCard v-for="(serie, index) in series" :key="index" :info='serie'></MyCard>
      </div>
    </section>
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

<style lang="scss">
section {
  padding: 10px;
}
.card-series {
  width: 90%;
  margin: 0px auto;
  display: flex;
  flex-wrap: wrap;
  justify-content: center; 
}
 h1 {
    text-align: center;
    color:lightseagreen;
    font-size: 40px;
  }
</style>