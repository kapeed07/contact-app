<template>
  <div>
    <div class="flex mb-8 justify-center items-center">
      <img
        class="w-16 "
        src="https://github.com/kapeed07/contact-app/blob/master/src/assets/icon.png?raw=true"
        alt=""
      />
      <p
        class="text-4xl tracking-widest font-mono  uppercase text-center text-gray-800"
      >
        Contacts
      </p>
    </div>
    <div class="mb-4">
      <input
        class="shadow-md mb-4 pl-4 w-full outline-none rounded-lg m-1 p-2"
        placeholder="Search..."
        type="text"
        autofocus
        v-model="searchTerm"
      />
    </div>
    <div class="contact-list">
      <list
        v-for="(contact, index) in filteredContacts"
        :key="index"
        :contact="contact"
      ></list>
    </div>
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
    axios.get("https://jsonplaceholder.typicode.com/users").then(({ data }) => {
      this.contacts = data;
    });
  },
  computed: {
    filteredContacts() {
      return this.contacts.filter(contact => {
        return contact.name
          .toLowerCase()
          .includes(this.searchTerm.toLowerCase());
      });
    }
  },
  components: {
    List
  }
};
</script>

<style>
.contact-list {
  -ms-overflow-style: none; /* Internet Explorer 10+ */
  scrollbar-width: none; /* Firefox */
}
.contact-list::-webkit-scrollbar {
  display: none; /* Safari and Chrome */
}

.contact-list {
  max-height: calc(100vh - 250px);
  overflow: auto;
}
</style>
