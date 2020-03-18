<template>
  <div>
    <p class="text-4xl tracking-widest font-mono  uppercase text-center text-gray-800">Contacts</p>
    <input class="shadow-md mb-4 pl-4 w-full outline-none rounded-lg m-1 p-2" placeholder="Search..." type="text" v-model="searchTerm">
    <list
      v-for="(contact, index) in filteredContacts"
      :key="index"
      :contact="contact"
    ></list>
  </div>
</template>

<script>
import axios from "axios";
import List from "./partials/list";

export default {
  name: "contact-index",
  data() {
    return {
      searchTerm: "",
      contacts: []
    };
  },
  created() {
    axios.get("https://jsonplaceholder.typicode.com/users")
    .then(({data}) => {
      this.contacts = data;
    })
  },
  computed: {
    filteredContacts() {
      return this.contacts.filter(contact => {
        return contact.name.toLowerCase().includes(this.searchTerm.toLowerCase())
      })
    }
  },
  components: {
    List
  }
};
</script>

<style></style>
