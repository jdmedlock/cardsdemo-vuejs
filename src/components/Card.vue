<template>
  <div>
    <div class="band"></div>
    <p class="content">{ member.firstName }, { member.lastName }</p>
  </div>
</template>

<script>
  export default {
    name: 'Card',
    props: {
      member: Object
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