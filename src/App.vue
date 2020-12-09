<template>
  <div className="App">
    <header className="App-header">
      <h1>VueJS Cards Demo</h1>
      <CardContainer />
    </header>
  </div>
</template>

<script>
  import CardContainer from './components/CardContainer.vue'

  export default {
    name: 'App',
    components: {
      CardContainer
    },
  }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

  h1 {
    font-weight: bold;
    font-style: italic;
    color: dodgerblue;
  }
</style>
