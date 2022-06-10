<template>
  <div class="body">
        <div class="head">
        <h2 class="name">Fierfud</h2>
        <button class="button 2"><nuxt-link to="/"><h3>Home</h3></nuxt-link></button>
        <button class="button 1" @click="changeTheme"><h3>Theme</h3></button>
        <button class="button 3"><nuxt-link to="/blogs"><h3>Blogs</h3></nuxt-link></button>
        <button class="button 3"><nuxt-link to="admin/#/"><h3>Create Blog</h3></nuxt-link></button>
    </div>
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
  head() {
    return {
      script: [{ src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }],
    };
  },
    methods:{
    changeTheme(){
      this.theme=this.theme==="Second"?"First":"Second";
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
      .head{
        display: grid;
        font-family: 'Titillium Web', sans-serif;
        height: 15%;
        gap: 1rem;
        grid-template-columns: 5fr repeat(4, 1fr);
    }
    .button{
        color: var(--quarternary);
        border: none;
        background-color: var(--primary);

    }
    .name{
        color: var(--tertiary);
        font-size: var(--h2);
    }
    a:link {
        color: var(--quarternary);
        text-decoration: none;
    }
    a:visited {
        color: var(--quarternary);
        text-decoration: none;}
</style>