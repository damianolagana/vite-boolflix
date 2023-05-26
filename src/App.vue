<script>
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
import { store } from './data/store';
import axios from 'axios'

export default {
  name: "App",
  components: {
    AppHeader,
    AppMain
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
  <main>
    <AppMain />
  </main>
</template>

<style scoped>
header {
  background-color: rgb(29, 27, 27);
  display: flex;
  align-items: center;
  height: 80px;
  justify-content: space-between;
  padding: 20px;
}
</style>
