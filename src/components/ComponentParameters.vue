<template lang="pug">
  table.table--component
    thead
      tr
        th Option
        th Effect
        th Remarks
    tbody
      tr(v-for="option in params")
        td(
          v-for="td in option",
          v-html="td"
        )
</template>

<script>
  export default {
    props: {
      params: Array,
      default: () => []
    }
  }
</script>

<style lang="stylus">
  .table
    &--component
      margin-bottom: 5rem
</style>