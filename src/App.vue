<template>
  <div id="app">
    <contacts></contacts>
  </div>
</template>

<script>
import Contacts from "./components/contacts/index"
export default {
  name: 'App',
  components: {
    Contacts
  }
}
</script>

<style>
body {
  background-color: rgb(241, 241, 239);
}
#app {
  width: 80%;
  margin: 50px auto;
}
</style>
