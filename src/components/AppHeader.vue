<script>
import { store } from '../data/store';

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
</template>

<style scoped></style>
