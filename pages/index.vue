<template>
  <div class="body">
    <Header class="heading" :theme="theme"></Header>
    <div class="frontWord">
      <h1>FierFud</h1>
      <h2>Discover, Explore, And Create Blogs About Food</h2>
      <nuxt-link to="/blogs">Explore</nuxt-link>
      <nuxt-link to="/admin">Create Your Own</nuxt-link>
    </div>
    <div class="frontImage">
      <img src="" alt="">
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data(){
    return{
      blogs:[],
      theme:"First"
    }
  },
  async fetch(){
    this.blogs = await this.$content('blog').fetch()
  },
}
</script>

<style scoped>
  .body{
    display: grid;
    grid-template-columns: 50% 50%;
    grid-template-rows: 100%;
  }
  .heading{
    grid-column: 1/-1;
  }
</style>