<template>
  <Card v-for="task in tasks" :task="task" :key="task.id"></Card>
</template>

<script>
  import Card from './Card.vue'

  export default {
    name: 'CardContainer',
    components: {
      Card
    },
    props: {
      tasks: Array
    },
  }

</script>
