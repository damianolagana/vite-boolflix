<script>
import { store } from '../data/store';


export default {
    name: "AppMain",
    data() {
        return {
            store,

        }
    },
    methods: {

    }

}



</script>

<template>
    <div id="moviesBox">
        <div v-for="movie in store.movies">
            <div>
                <img :src="`${this.store.urlCover}${movie.poster_path}`" alt="">
            </div>
            <div>
                <p><span>Titolo:</span> {{ movie.title }}</p>
                <p><span>Titolo originale:</span> {{ movie.original_title }}</p>
                <p><span> Language:</span> {{ movie.original_language }}</p>
                <p><span>Vote:</span> {{ movie.vote_average }}</p>
            </div>
        </div>

    </div>
</template>

<style scoped>
#moviesBox {
    display: flex;
    flex-wrap: wrap;
    color: white;
}

#moviesBox>div {
    width: calc(100%/5);
    border: 1px solid white;
    padding: 10px;
    text-align: center;
}

span {
    font-weight: 600;
}

img {
    width: 100%;
}
</style>
