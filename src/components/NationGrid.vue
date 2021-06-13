<template>

    <div class="nation-grid">

        <!-- loop through nations
            nations array received as props from parent component -->
        <NationCard v-for="nation in filterNations" :key="nation.numericCode" :nation="nation"  />

    </div>

</template>

<script>
import NationCard from '../components/NationCard.vue'

export default {
    name: "NationGrid",
    components: {
        NationCard
    },
    props: {
        nations: [],
        search: {
            type: String
        },
        region: {
            type: String
        }
    },
    data: function() {

    },
    computed: {
        // filter nations based on search query
        filterNations: function() {
            return this.nations.filter((nation) => {
                if (nation.region === this.region || this.region === 'all' || this.region === '' || this.region === null) {
                    return nation.name.toLowerCase().includes(this.search.toLowerCase());
                } else {
                    return false;
                }
                
            });
        }
    },
}
</script>

<style scoped>

.nation-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-column-gap: 3em;
    grid-row-gap: 3em;
}

</style>