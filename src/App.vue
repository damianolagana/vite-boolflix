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

  },

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
