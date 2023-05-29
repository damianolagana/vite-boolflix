<script>
import { store } from '../data/store';
import CountryFlag from 'vue-country-flag-next'

export default {
    name: "AppMain",
    components: {
        CountryFlag
    },
    data() {
        return {
            store,

        }
    },
    methods: {
        getLanguageFlag(lang) {
            if (lang == "en") {
                return "gb";
            }
            return lang;

        }
    }

}



</script>

<template>
    <div>
        <h2>Movies</h2>
        <div class="contentBox">
            <div v-for="movie in store.movies">
                <div>
                    <img :src="`${this.store.urlCover}${movie.poster_path}`" alt="">
                </div>
                <div>
                    <p><span>Titolo:</span> {{ movie.title }}</p>
                    <p><span>Titolo originale:</span> {{ movie.original_title }}</p>
                    <p><span> Language:</span> <country-flag :country='getLanguageFlag(movie.original_language)'
                            size='small' />
                    </p>
                    <p><span>Vote:</span> {{ movie.vote_average }}</p>
                </div>
            </div>

        </div>
        <h2>Series</h2>
        <div class="contentBox">
            <div v-for="serie in store.series">
                <div>
                    <img :src="`${this.store.urlCover}${serie.poster_path}`" alt="">
                </div>
                <div>
                    <p><span>Titolo:</span> {{ serie.name }}</p>
                    <p><span>Titolo originale:</span> {{ serie.original_name }}</p>
                    <p><span> Language:</span> <country-flag :country='getLanguageFlag(serie.original_language)'
                            size='small' />
                    </p>
                    <p><span>Vote:</span> {{ serie.vote_average }}</p>
                </div>
            </div>

        </div>

    </div>
</template>

<style scoped>
h2 {
    padding: 1rem 0 1rem 0;
}

.contentBox {
    display: flex;
    color: white;
    overflow-x: scroll;
}

.contentBox::-webkit-scrollbar {
    display: none;
}

.contentBox>div {

    border: 1px solid white;
    padding: 10px;
    text-align: center;
    width: calc(100%/3)
}

.visible {
    display: block;
}

.invisible {
    display: none;
}

span {
    font-weight: 600;
}
</style>
