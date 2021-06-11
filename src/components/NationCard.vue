<template>
  
    <div class="nation-card">
        <img :src="nation.flag" alt="" class="flag-image">
        <div class="nation-card__info">
            <h3>{{nation.name}}</h3>
            <p><strong>Population:</strong> {{nation.population.toLocaleString()}}</p>
            <p><strong>Region:</strong> {{nation.region}}</p>
            <p><strong>Capital:</strong> {{nation.capital}}</p>
        </div>
    </div>

</template>

<script>
export default {
    name: 'NationCard',
    props: {
        nation: []
    },
    data: function() {

    }
}
</script>

<style scoped>

.nation-card {
    background: white;
    box-shadow: 0px 0px 10px 0px rgba(0,0,0,0.1);
    border-radius: 5px;
}

.nation-card__info {
    padding: 10px 30px 30px 30px;
}

.flag-image {
    width: 100%;
    border-radius: 5px 5px 0 0;
}

</style>