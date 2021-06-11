<template>
  <Navbar />
  <div class="container">
    <div class="searchfilter">
      <SearchBar />
    </div>
    <NationCard />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import SearchBar from './components/SearchBar.vue'
import NationCard from './components/NationCard.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    SearchBar,
    NationCard
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

.container {
  max-width: 1440px;
  padding: 0 80px;
}

.searchfilter {
  padding: 50px 0px;

  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

</style>
