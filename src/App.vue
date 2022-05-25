<template>
  <HomePage msg="Thank you for using our product. We're glad you're with us."/>
</template>

<script>
  import HomePage from './components/HomePage'

  export default {
    name: 'App',
    components: {
      HomePage
    },mounted() {
      document.querySelector('title').textContent = document.getElementById('fullName').innerText
    }
  }
</script>

<style lang="scss">
  @import '~@/../mdb/scss/index.free.scss';

  body {
    background-color: #E0E0E0;
  }

  #app {
    font-family: Roboto, Helvetica, Arial, sans-serif;
  }

</style>
