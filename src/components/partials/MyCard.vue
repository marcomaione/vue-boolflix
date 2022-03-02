<template>
    <div class="card">
        <img v-if="info.poster_path" :src="`https://image.tmdb.org/t/p/w342${info.poster_path}`">
        <img v-else :src="'https://www.salonlfc.com/wp-content/uploads/2018/01/image-not-found-scaled.png'">
        <h3>{{getTitle()}}</h3>
        <h3>{{info.original_title}}</h3>
        <div class="flag">
            <img v-if="languages.includes(info.original_language)" :src="require('../../assets/flags/' + info.original_language + '.png')">
            <span v-else>{{info.original_language}}</span>
        </div>
        <div class="star">
            <i v-for="i in 5" :key="i" class="fa-star" :class="(i<getstar())?'fa-solid' : 'fa-regular'"></i>
        </div>
    </div>
</template>

<script>
export default {
    name:'MyCard',
    props: {
        'info': Object

    },
    data() {
        return {
            languages: ['en', 'it'],
        }
    },
    methods: {
        getTitle() {
            if (this.info.title) {
                return this.info.title;
            }else {
                return this.info.name;
            }
        },
        getstar() {
            return Math.ceil(this.info.vote_average / 2);
        }
    }

}
</script>

<style lang="scss">
.card {
    width: 300px;
    margin:25px 10px;
    h3 {
        color:rgb(218, 211, 211);
    }
}
.card img {
    max-width: 300px;
    border: solid 1px wheat;
}
.flag img {
    max-width: 30px;
}.star i {
    color: gold;
}


</style>