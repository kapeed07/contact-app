<template>
  <div>
    <div
      :class="`flex justify-between hover:shadow-xl items-center shadow text-gray-900 w-full border border-${color}-600 bg-${color}-200 p-3 pl-5 mb-3 rounded-md`"
    >
      <div class="flex">
        <div
          :class="`circle w-6 h-6 bg-${color}-300 border border-${color}-500 rounded-full`"
        >
          <img :src="`https://robohash.org/${contact.username}`" alt="" />
        </div>
        <p class="ml-3">{{ contact.name }}</p>
      </div>

      <p>{{ contact.phone }}</p>

      <span class="action-buttons">
        <div>
          <!-- @click="$emit('delete', contact.id)" -->
          <!-- <i
            class="cursor-pointer fas fa-ellipsis-v"
          ></i> -->
        </div>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: "contact-list",
  props: ["contact"],
  data() {
    return {
      color: "pink"
    }
  }
};
</script>

<style>
.action-buttons {
  min-width: 35px;
}
</style>
