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
#app {
  width: 80%;
  margin: 50px auto;
}
</style>
