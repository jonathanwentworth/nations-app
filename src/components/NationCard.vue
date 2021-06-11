<template>
    <div class="nation-grid">
        <div class="nation-card" v-for="nation of nations" :key="nation.numericCode">
            <img :src="nation.flag" alt="" class="flag-image">
            <div class="nation-card__info">
                <h3>Name: {{nation.name}}</h3>
                <p>Population: {{nation.population}}</p>
                <p>Region: {{nation.region}}</p>
                <p>Capital: {{nation.capital}}</p>
            </div>
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
            nations: {}
        }
    },
    async mounted() {
        try {
            const res = await axios.get('https://restcountries.eu/rest/v2/all');

            this.nations = res.data;
        }
        catch(e) {
            console.log(e);
        }
    }
}
</script>

<style>

.nation-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-column-gap: 3em;
    grid-row-gap: 3em;
}

.nation-card {
    background: white;
    box-shadow: 0px 0px 10px 0px rgba(0,0,0,0.1);
    border-radius: 5px;
}

.nation-card__info {
    padding: 30px;
}

.flag-image {
    width: 100%;
    border-radius: 5px 5px 0 0;
}

</style>
