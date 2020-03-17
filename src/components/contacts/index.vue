<template>
  <div>
    <h1>Contacts</h1>
    <list
      v-for="(contact, index) in contacts"
      :key="index"
      :contact="contact"
    ></list>
  </div>
</template>

<script>
import List from "./partials/list";

export default {
  name: "contact-index",
  data() {
    return {
      contacts: [
        {
          first_name: "Deepak",
          last_name: "Bhardwaj",
          mobile: "9953575646"
        },
        {
          first_name: "Kapeed",
          last_name: "Bhardwaj",
          mobile: "9999999999"
        }
      ]
    };
  },
  components: {
    List
  }
};
</script>

<style></style>
