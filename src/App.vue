<template>
  <div className="App">
    <header className="App-header">
      <h1>React Cards Demo</h1>
      <CardContainer team=team />
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
    data() {
      const team = [
          {id: 1, firstName: "John", lastName: "Roku"},
          {id: 2, firstName: "Rakesh", lastName: "Singh"},
          {id: 3, firstName: "Julie", lastName: "Eaker"},
          {id: 4, firstName: "Carla", lastName: "Sanchez"},
          {id: 5, firstName: "Javier", lastName: "Smith"}
      ]
      return team
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
  margin-top: 60px;
}

  h1 {
    font-weight: bold;
    font-style: italic;
    color: dodgerblue;
  }
</style>
