<template>

    <div class="search">

        <!-- v-model binds data to searchTerms
            @input calls the method search() in order to emit data to parent component -->
        <input @input="search" type="text" class="searchTerm" placeholder="Search for nation..." v-model="searchTerm">

    </div>

</template>

<script>
export default {
    name: 'SearchBar',
    props: {},
    data: function() {
        return {
            searchTerm: ""
        }
    },
    methods: {
        // emit search query data to parent component
        search() {
            this.$emit('input', this.searchTerm);
        }
    }
}
</script>

<style scoped>

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