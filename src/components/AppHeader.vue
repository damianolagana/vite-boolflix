<script>
import { store } from '../data/store';

export default {
    name: "AppHeader",
    data() {
        return {
            store
        }
    },
    mounted() {
        console.log(this.store.fullAPI)
    }
}



</script>

<template>
    <div>
        <input type="text" placeholder="Cerca">
        <button>Search</button>
    </div>
</template>

<style scoped></style>
