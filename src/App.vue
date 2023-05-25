<script>
import AppHeader from './components/AppHeader.vue'
import { store } from './data/store';

export default {
  name: "App",
  components: {
    AppHeader
  },
  data() {
    return {
      store
    }
  }
}
</script>

<template>
  <header>
    <AppHeader />
  </header>
</template>

<style scoped></style>
