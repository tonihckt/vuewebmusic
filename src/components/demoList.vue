<template lang="pug">
  b-list-group
    b-list-group-item(v-for='item in items')
    | {{ item.message }}
</template>

<script>
export default {
  items: [
    { message: "Nokia 8" },
    { message: "OnePlus 5T" },
    { message: "Samsung Galaxy S9" }
  ]
};
</script>

<style lang="stylus" scoped></style>
