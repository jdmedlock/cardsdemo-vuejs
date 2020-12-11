<template>
  <div className="App">
    <header className="App-header">
      <h1>VueJS Cards Demo</h1>
      <CardContainer :tasks="getTasks()"/>
    </header>
  </div>
</template>

<script>
  import axios from 'axios'
  import { createStore } from 'vuex'
  import CardContainer from './components/CardContainer.vue'

  const EMPTY = 'EMPTY'
  const FAILED = 'FAILED'
  const LOADED = 'LOADED'

  // Define the store to contain the `tasks` & associated methods
  const tasks = createStore({
    state: {
      isTasksLoaded: EMPTY,
      tasks: []
    },
    mutations: {
      SET_STATUS(state, status) {
        state.isTasksLoaded = status
      },
      SET_TASKS(state, tasks) {
        state.tasks = tasks
      }
    },
    actions: {
      // Retrieve the array of task objects from the BE server
      fetchTasks(context) {
        const config = {
          method: 'get',
          url: 'http://localhost:5000/splash',
          headers: { }
        }
        axios(config)
          .then((response) => {
            context.commit('SET_STATUS', LOADED)
            context.commit('SET_TASKS', response.data)
          })
          .catch((error) => {
            context.commit('SET_STATUS', FAILED)
            console.log({error})
          })
      }
    }
  })

  // Define is App component & it's methods. Checkout that `setup` is returning
  // the `getTasks` method that returns the array containing the task objects.
  // that have been retrieved from the BE server.
  export default {
    name: 'App',
    components: {
      CardContainer
    },
    setup() {
      //const store = useStore()
      const getTasks = () => tasks.state.tasks

      tasks.dispatch('fetchTasks')
      return { 
        getTasks
      }
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
