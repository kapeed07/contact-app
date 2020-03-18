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
    <div class="mb-4 relative">
      <input
        class="search-box shadow-md mb-4 pl-4 pr-4 p-2 w-full outline-none rounded-lg"
        type="text"
        placeholder="Search"
        autofocus
        v-model="searchTerm"
      />
      <p>Showing {{ count }} contacts</p>
    </div>
    <div class="contact-list">
      <list
        v-for="contact in filteredContacts"
        :key="contact.id"
        :contact="contact"
        @delete="deleteContact"
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
    axios
      .get("https://jsonplaceholder.typicode.com/users")
      .then(({ data }) => (this.contacts = data));
  },
  computed: {
    count() {
      return this.filteredContacts.length;
    },
    filteredContacts() {
      return this.contacts.filter(contact => {
        return contact.name
          .toLowerCase()
          .includes(this.searchTerm.toLowerCase());
      });
    }
  },
  methods: {
    deleteContact(id) {
      let _contacts = [...this.contacts];
      this.contacts = _contacts.filter(contact => contact.id != id);
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
.search-label {
  top: 12px;
  left: 20px;
  font-size: 14px;
  transition: all 0.1s ease;
}
.search-box:focus + .search-label {
  top: -21px;
  left: 6px;
  font-size: 16px;
}
.search-box:valid + .search-label {
  top: -21px;
  left: 6px;
  font-size: 16px;
}
</style>
