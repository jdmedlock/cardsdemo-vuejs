<template>
  <Card v-for="member in team" v-bind:member="member" v-bind:key="member.id"></Card>
</template>

<script>
  import Card from './Card.vue'

  export default {
    name: 'CardContainer',
    components: {
      Card
    },
    setup() {
      const team = [
          {id: 1, firstName: "John", lastName: "Roku"},
          {id: 2, firstName: "Rakesh", lastName: "Singh"},
          {id: 3, firstName: "Julie", lastName: "Eaker"},
          {id: 4, firstName: "Carla", lastName: "Sanchez"},
          {id: 5, firstName: "Javier", lastName: "Smith"}
      ]
      console.log({team})
      return { team }
    }
  }
</script>
