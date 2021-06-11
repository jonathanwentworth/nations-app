<template>
  <div class="nation-card">
      <img src="" alt="">
      <div class="nation-card__info">
          <h3>{{name}}</h3>
          <p>Population: {{population}}</p>
          <p>Region: {{region}}</p>
          <p>Capital: {{capital}}</p>
      </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
    name: "NationCard",
    props: {

    },
    data: function() {
        return {
            name: "",
            population: 0,
            region: "",
            capital: ""
        }
    },
    async mounted() {
        try {
            const res = await axios.get('https://restcountries.eu/rest/v2/alpha/col');

            this.name = res.data.name;
            this.population = res.data.population;
            this.region = res.data.region;
            this.capital = res.data.capital;
        }
        catch(e) {
            console.log(e);
        }
    }
}
</script>

<style>

.nation-card {
    background: white;
    padding: 40px;
    box-shadow: 0px 0px 10px 0px rgba(0,0,0,0.1);
    border-radius: 2px;
}

</style>
