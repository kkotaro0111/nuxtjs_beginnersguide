<template lang="pug">
  div
    span single layout
    AppNavigation
    hr
    nuxt
    nuxt-link(to="/") トップへ戻る
    hr
    footer footer
    //
</template>

<script>
  import AppNavigation from '~/components/AppNavigation.vue'

export default {
  name: "",
  components:{
    AppNavigation
  }

}
</script>

<style lang="sass" scoped>

</style>
