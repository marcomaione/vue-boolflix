<template>
    <li class="card">
        <div>{{film.title}}</div>
        <div>{{film.original_title}}</div>
        <div>
            <img v-if="languages.includes(film.original_language)" :src="require('../../assets/flags/' + film.original_language + '.png')">
            <span v-else>{{film.original_language}}</span>
        </div>
        <div>{{film.vote_average}}</div>
    </li>
</template>

<script>
export default {
    name:'FilmCard',
    props: {
        'film': Object

    },
    data() {
        return {
            languages: ['en', 'it'],
        }
    }

}
</script>

<style lang="scss">

</style>