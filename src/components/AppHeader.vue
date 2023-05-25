<script>
import { store } from '../data/store';
import axios from 'axios'

export default {
    name: "AppHeader",
    data() {
        return {
            store,
            searchedMovie: ""
        }
    },
    methods: {
        findMovies() {
            console.log(this.searchedMovie)
            this.store.fullAPI += this.store.query + this.searchedMovie;
            console.log(this.store.fullAPI)

            axios.get(this.store.fullAPI).then(answer => {
                console.log(answer)
                this.store.movies = answer.data.results
                console.log(store.movies)

            })

            this.searchedMovie = ""
        }
    }

}



</script>

<template>
    <div>
        <input type="text" placeholder="Cerca" v-model="searchedMovie">
        <button @click="findMovies()">Search</button>
    </div>
    <div id="moviesBox">
        <div v-for="movie in store.movies">
            <h2>Movie</h2>
            <ul>
                <li>{{ movie.title }}</li>
                <li>{{ movie.original_title }}</li>
                <li>{{ movie.original_language }}</li>
                <li>{{ movie.vote_count }}</li>
            </ul>
        </div>

    </div>
</template>

<style scoped>
#moviesBox {
    display: flex;
    flex-wrap: wrap;
    width: 1200px;
}

#moviesBox>div {
    width: calc(100%/5);
}
</style>
