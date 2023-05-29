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
        startSearching() {
            this.findMovies();
            this.findSeries();

            this.searchedMovie = ""
        },

        findMovies() {
            console.log(this.searchedMovie)
            const fullMoviesUrl = `${this.store.urlApi}movie?${this.store.apiKey}&query=${this.searchedMovie}`


            axios.get(fullMoviesUrl).then(answer => {
                console.log(answer)
                this.store.movies = answer.data.results
                console.log(store.movies)
            })


        },
        findSeries() {
            const fullSeriesUrl = `${this.store.urlApi}tv?${this.store.apiKey}&query=${this.searchedMovie}`

            console.log("url serie", fullSeriesUrl)
            axios.get(fullSeriesUrl).then(answer => {
                console.log("le serie sono:", answer)
                this.store.series = answer.data.results
                console.log("array series", store.series)
            })
        }
    }

}



</script>

<template>
    <div>
        <h2>BOOLFLIX</h2>
    </div>
    <div id="navBar">
        <input type="text" placeholder="Cerca" v-model="searchedMovie">
        <button @click="startSearching()">Search</button>
    </div>
</template>

<style scoped>
#navBar {
    width: 30%;
    padding: 10px;
}

h2 {
    color: red;
}
</style>
