<template>
  <div id="app">
    <CoponentA></CoponentA>
    <CoponentB></CoponentB>
  </div>
</template>

<script>
import CoponentA from '@/components/ComponentA.vue'
import CoponentB from '@/components/ComponentB.vue'
export default {
  components: {
    CoponentA,
    CoponentB
  }
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
