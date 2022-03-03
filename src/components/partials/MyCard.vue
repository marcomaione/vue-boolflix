<template>
    <div class="flip-card">
        <div class="flip-card-inner">
            <div class="flip-card-front">
                <img v-if="info.poster_path" :src="`https://image.tmdb.org/t/p/w342${info.poster_path}`">
                <img v-else :src="'https://www.salonlfc.com/wp-content/uploads/2018/01/image-not-found-scaled.png'">
            </div>
            <div class="flip-card-back">
                <h3>{{getTitle()}}</h3>
                <h3>{{info.original_title}}</h3>
                <div class="flag">
                    <img v-if="languages.includes(info.original_language)" :src="require('../../assets/flags/' + info.original_language + '.png')">
                    <span v-else>{{info.original_language}}</span>
                </div>
                <div class="star">
                    <i v-for="i in 5" :key="i" class="fa-star" :class="(i<getstar())?'fa-solid' : 'fa-regular'"></i>
                </div>
                <div>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolores at consectetur voluptates cumque fugiat debitis, veniam ducimus doloribus? Dolore nobis veritatis mollitia rerum perspiciatis maiores ipsam doloribus reprehenderit eius cum.</p>
                </div>
            </div>
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

<style scoped lang="scss">
h3 {
    color:rgb(218, 211, 211);
}
.flag img {
    max-width: 30px;
}.star i {
    color: gold;
}
.flip-card-front {
    img {
        width: 100%;
        height: 500px;
        object-fit:cover;
        border: solid 1px wheat;

    }
}

/* The flip card container - set the width and height to whatever you want. We have added the border property to demonstrate that the flip itself goes out of the box on hover (remove perspective if you don't want the 3D effect */
.flip-card {
  background-color: transparent;
  width: 300px;
  height: 500px;
  perspective: 1000px; /* Remove this if you don't want the 3D effect */
  margin:25px 10px;
}

/* This container is needed to position the front and back side */
.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}

/* Do an horizontal flip when you move the mouse over the flip box container */
.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

/* Position the front and back side */
.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden; /* Safari */
  backface-visibility: hidden;
}

/* Style the front side (fallback if image is missing) */
.flip-card-front {
  background-color: #bbb;
  color: black;
}

/* Style the back side */
.flip-card-back {
  background-color: black;
  color: white;
  transform: rotateY(180deg);
  border: solid 1px wheat;
}


</style>

