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
            <h2>Movie</h2>
            <div>
                <img src="" alt="">
            </div>
            <div>
                <p>{{ movie.title }}</p>
                <p>{{ movie.original_title }}</p>
                <p>{{ movie.original_language }}</p>
                <p>{{ movie.vote_count }}</p>
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
</style>
