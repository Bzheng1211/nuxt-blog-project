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
      theme:"First"
    }
  },
}
</script>

<style scoped>
  .body{
    display: grid;
    background-color: var(--primary);
    min-height: 100%;
    font-family: 'Titillium Web', sans-serif;
  }
  .heading{
    grid-column: 1/-1;
  }
  .frontWord{
    height: 100%;
  }
</style>