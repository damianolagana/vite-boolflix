<script>
import AppHeader from './components/AppHeader.vue'
import { store } from './data/store';
import axios from 'axios'

export default {
  name: "App",
  components: {
    AppHeader
  },
  data() {
    return {
      store
    }
  },
  methods: {
    getFullAPI() {
      this.store.fullAPI = this.store.urlApi + this.store.apiKey
    }
  },
  mounted() {

    this.getFullAPI()
    console.log(this.store.fullAPI)

    axios.get(this.store.fullAPI).then(answer => {
      console.log(answer)

    })
  }
}
</script>

<template>
  <header>
    <AppHeader />
  </header>
</template>

<style scoped></style>
