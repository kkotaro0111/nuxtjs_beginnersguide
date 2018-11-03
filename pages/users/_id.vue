<template lang="pug">
  section.container
    div
      h3 {{user.id}}
      img(:src="user.profile_image_url" width="120" alt="")
      p {{user.description || 'No description'}}
      p
        nuxt-link(to="/")
          small
            b トップへ戻る
      h3 {{user.id}} さんの投稿一覧
      ul
        li(v-for="item in items" :key="item.id")
          h4
            span {{item.title}}
          div {{item.body.slice(0, 130)}} ...
          p
            a(target="_blank" :href="item.url") {{item.url}}
</template>

<script>
  import {mapGetters} from 'vuex';

  export default {
    head(){
      return {
        title: this.user.id
      }
    },
    async asyncData({ route, store, redirect }){
      console.log( '----', store.getters['users'], route.params.id, store.getters['users'][route.params.id] );
      if( store.getters['users'][route.params.id] ){
        // exist
        return;
      }
      try {
        await store.dispatch('fetchUserInfo', {id: route.params.id})
      }catch(e){
        //redirect('/');
      }
    },
    computed: {
      user(){
        console.log('****',  this.users, this.$route.params.id, this.users[this.$route.params.id]);
        return this.users[this.$route.params.id]
      },
      items(){
        return this.userItems[this.$route.params.id] || [];
      },
      ...mapGetters(['users', 'userItems'])
    }

  }
</script>

<style lang="sass" scoped>

</style>
