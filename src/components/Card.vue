<template>
  <div>
    <div class="band"></div>
    <p class="content">Title:{{ task.title }}  -  Location:{{task.location}}  -  Status:{{ task.status }}</p>
  </div>
</template>

<script>
  export default {
    name: 'Card',
    props: {
      task: Object
    }
  }
</script>

<style>
  .band { 
    background: lightgray;
    width: 32px;
  }

  .content { 
    background: white;
  }
</style>