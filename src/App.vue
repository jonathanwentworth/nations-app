<template>
  <Navbar />
  <div class="container">
    <NationCards />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import NationCards from './components/NationCards.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    NationCards
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
}

body {
  margin: 0;
  background-color: hsl(0, 0%, 98%);
}

p {
  font-size: 14px;
  line-height: 1.7;
  margin: 0;
}

.container {
  max-width: 1440px;
  padding: 0 80px;
  margin: 0 auto;
}

.searchfilter {
  padding: 50px 0px;

  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

</style>
