<template>
  <div>
    <div
      @mousemove="isHover = true"
      @mouseleave="isHover = false"
      class="flex justify-between items-center shadow text-indigo-900 w-full border bg-indigo-200 border-indigo-500 p-2 mb-3 rounded"
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

      <span class="action-buttons">
        <div v-if="isHover">
          <i
            @click="$emit('delete', contact.id)"
            class="cursor-pointer text-red-600 far fa-trash-alt"
          ></i>
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
      isHover: false
    };
  }
};
</script>

<style>
.action-buttons {
  min-width: 35px;
}
</style>
