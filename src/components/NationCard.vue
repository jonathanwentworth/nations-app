<template>
  <div class="nation-card">
      <img src="" alt="">
      <div class="nation-card__info">
          <h3>Germany</h3>
          <p>Population: 2312123</p>
          <p>Region: Europe</p>
          <p>Capital: Berlin</p>
      </div>
  </div>
</template>

<script>
export default {
    name: "NationCard",
    props: {

    },
    data: function() {
        return {

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
