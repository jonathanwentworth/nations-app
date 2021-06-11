<template>
    <div class="search">
        <input type="text" class="searchTerm" placeholder="What are you looking for?" v-model="search">
        <p>Input: {{search}}</p>
    </div>
    <div class="nation-grid">
        <div class="nation-card" v-for="nation in filterNations" :key="nation.numericCode">
            <img :src="nation.flag" alt="" class="flag-image">
            <div class="nation-card__info">
                <h3>{{nation.name}}</h3>
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
    name: "NationCards",
    props: {
    },
    data: function() {
        return {
            nations: {},
            search: ''
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
    },
    computed: {
        filterNations() {
            return this.nations.filter(nation => nation.name.includes(this.search));
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

.search {
    margin: 50px 0;
}

.searchTerm {
    padding: 18px 24px;
    min-width: 250px;

    border: none;
    border-radius: 2px;

    background-color: white;
    box-shadow: 0px 0px 10px 0px rgba(0,0,0,0.1);
}

</style>