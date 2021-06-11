<template>

    <div class="search">
        <input type="text" class="searchTerm" placeholder="What are you looking for?" v-model="searchTerm">
        <p>Input: {{searchTerm}}</p>
    </div>

</template>

<script>
export default {
    name: 'SearchBar',
    props: {

    },
    data: function() {
        return {
            searchTerm: ""
        }
    }
}
</script>

<style>

.searchTerm {
    padding: 18px 24px;
    min-width: 250px;

    border: none;
    border-radius: 2px;

    background-color: white;
    box-shadow: 0px 0px 10px 0px rgba(0,0,0,0.1);
}

</style>