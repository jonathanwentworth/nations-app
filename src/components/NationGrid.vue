<template>

    <div class="nation-grid">
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
        }
    },
    data: function() {

    },
    computed: {
        filterNations: function() {
            return this.nations.filter((nation) => {
                return nation.name.toLowerCase().match(this.search.toLowerCase());
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