<template>
  <div id="app">
    <contacts></contacts>
    <div class="bg-red-400 p-3 pl-12 pr-12 text-white watermark absolute">
      @kapeed07
    </div>
  </div>
</template>

<script>
import Contacts from "./components/contacts/index";
export default {
  name: "App",
  components: {
    Contacts
  }
};
</script>

<style>
body {
  background-color: rgb(241, 241, 239);
}
.watermark {
  transform: rotate(-45deg);
  top: 20px;
  left: -45px;
}
#app {
  width: 80%;
  margin: 50px auto;
}
</style>
