<template lang="pug">
  div
    h2 認証が必要なページ
    p
      |Cookie の 'credential' 値が Truthy な場合のみアクセス可能です。
      br
      nuxt-link(to="/") トップへ戻る
  //
</template>

<script>
  export default {
    name: ""
  }
</script>

<style lang="sass" scoped>

</style>
