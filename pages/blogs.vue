<template>
  <div class="blogshowcase" :class="theme==='Second'?'First':'Second'">
    <div class="head">
        <h2 class="name">Fierfud</h2>
        <button class="button 2"><nuxt-link to="/"><h3>Home</h3></nuxt-link></button>
        <button class="button 1" @click="changeTheme"><h3>Theme</h3></button>
        <button class="button 3"><nuxt-link to="/blogs"><h3>Blogs</h3></nuxt-link></button>
        <button class="button 3"><nuxt-link to="/admin"><h3>Create Blog</h3></nuxt-link></button>
    </div>
    <form id="search">
      <input name="query" placeholder="Search" v-model="searchQuery">
    </form>
    <div class="blogpreview" v-for="blog in blogs" :key="blog.title">
      <img src="" alt="">
      <nuxt-link :to="{ name: 'slug' , params:{slug:slug} }"><h3>{{blog.title}}</h3></nuxt-link>
      <p>{{blog.description}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlogPage',
  data(){
    return {
      searchQuery:"",
      theme:"First",
      blogs:[]
    }
  },
  computed:{
    filteredBlogs: function(){
      return this.blogs.filter((blog)=>{
        return blog.title.toLowerCase().match(this.searchQuery.toLowerCase())
      })
    }
  },
  methods:{
    changeTheme(){
      this.theme=this.theme==="Second"?"First":"Second";
      }
    },
  async fetch(){
    this.blogs = await this.$content('blog').fetch()
  },
}
</script>

<style>
.blogshowcase{
  display: grid;
  grid-template-columns: 25%;
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
        text-decoration: none;
    }
</style>