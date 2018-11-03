<template lang="pug">
  ul
    li
      nuxt-link(to="/") home
    li
      nuxt-link(to="/child") child

</template>

<script>
  export default {
    name: "AppNavigation"
  }
</script>

<style scoped>

</style>
