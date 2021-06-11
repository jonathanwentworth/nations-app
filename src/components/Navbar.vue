<template>

  <div class="navbar">
    <div class="container nav">
      <h1>{{title}}</h1>
      <div class="theme-switcher">
        <p>{{theme}}</p>
      </div>
    </div>
  </div>

</template>

<script>

export default {
  name: 'Navbar',
  props: {
    
  }, 
  data: function() {
    return {
      title: "Where in the world?",
      theme: "Dark Mode"
    }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.navbar {
  width: 100%;

  background: white;
  box-shadow: 0px 4px 10px 0px rgba(0,0,0,0.1);
}

.nav {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
}

</style>
