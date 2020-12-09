<template>
  <div>
  <Card v-for="member in team" v-bind:member={{ member }} v-bind:key={{ member.id }} />
  </div>
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
