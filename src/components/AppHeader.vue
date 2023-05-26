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
        <h2>BOOLFLIX</h2>
    </div>
    <div id="navBar">
        <input type="text" placeholder="Cerca" v-model="searchedMovie">
        <button @click="findMovies()">Search</button>
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
