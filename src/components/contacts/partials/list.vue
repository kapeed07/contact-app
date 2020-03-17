<template>
  <div>
    {{contact.first_name}} | {{contact.last_name}} | {{contact.mobile}}
  </div>
</template>

<script>
export default {
  name: "contact-list",
  props: ["contact"]
}
</script>

<style>

</style>