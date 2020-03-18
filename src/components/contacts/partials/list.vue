<template>
  <div>
    <div
      class="shadow text-indigo-900 w-full border bg-indigo-200 border-indigo-500 p-2 mb-3 rounded flex justify-between items-center"
    >
      <div class="flex">
        <div
          class="circle w-6 h-6 bg-gray-200 border border-gray-500 rounded-full"
        >
          <img :src="`https://robohash.org/${contact.username}`" alt="" />
        </div>
        <p class="ml-3">{{ contact.name }}</p>
      </div>
      <p>{{ contact.phone }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "contact-list",
  props: ["contact"]
};
</script>

<style></style>
