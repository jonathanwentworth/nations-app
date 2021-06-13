<template>
  <div>
      <select v-model="selectedRegion" @change="selectRegion">
          <option selected disabled hidden>Filter By Region</option>
          <option value="all">ALL REGIONS</option>
          <option value="Africa">Africa</option>
          <option value="Americas">Americas</option>
          <option value="Asia">Asia</option>
          <option value="Europe">Europe</option>
          <option value="Oceania">Oceania</option>
      </select>
  </div>
</template>

<script>
export default {
    name: 'Vue',
    data() {
        return {
            selectedRegion: null
        }
    },
    methods: {
        selectRegion() {
            this.$emit('select-region', this.selectedRegion);
            console.log(this.selectedRegion);
        }
    }
}
</script>

<style>

select {
    padding: 1rem;
    margin-bottom: 30px;
    border: none;
    border-radius: 0;
    box-shadow: 0 0 10px 0 rgba(0,0,0,0.1);
}

</style>