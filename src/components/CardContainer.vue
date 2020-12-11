<template>
  <Card v-for="member in team" :member="member" :key="member.id"></Card>
</template>

<script>
  import Card from './Card.vue'

  export default {
    name: 'CardContainer',
    components: {
      Card
    },
    props: {
      team: Array
    }
  }
</script>
