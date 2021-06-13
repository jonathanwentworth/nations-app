<template>

  <Navbar />

  <div class="container">
    <!-- call inputChanged function on event emitted from SearchBar component -->
    <SearchBar @input="inputChanged" />
    <NationFilter @select-region="selectRegion" />
    <!-- pass data to child component using :nations="nations" -->
    <NationGrid :nations="nations" :search="search" :region="region" />
  </div>

</template>

<script>
// using axios to get API data
import axios from 'axios';

// import components
import Navbar from './components/Navbar.vue'
import NationGrid from './components/NationGrid.vue'
import SearchBar from './components/SearchBar.vue'
import NationFilter from './components/NationFilter.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    NationGrid,
    SearchBar,
    NationFilter
  },
  data: function() {
    return {
      nations: [],
      search: '',
      region: ''
    }
  },
  // fetch API data. mounted() executes before creating the component
  async mounted() {
      try {
          const res = await axios.get('https://restcountries.eu/rest/v2/all');
          this.nations = res.data;
      }
      catch(e) {
          console.log(e);
      }
  },
  // receiving search data emitted from SearchBar component
  methods: {
    inputChanged(search) {
      this.search = search;
    },
    selectRegion(region) {
      this.region = region;
    }
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
  padding-bottom: 100px;
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
