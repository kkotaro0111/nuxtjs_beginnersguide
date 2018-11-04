<template lang="pug">
  div
    h2 ログインページ
    p
      button(type="button" @click="login") ログイン
      br
      nuxt-link(to="/") トップページへ戻る

  //
</template>

<script>
  import Cookies from 'universal-cookie'

  export default {
    name: "",
    methods: {
      login(){
        const cookies = new Cookies();
        cookies.set('credential', 'true', {maxAge: 90});
        this.$router.push('/');
      }
    }
  }
</script>

<style lang="sass" scoped>

</style>
