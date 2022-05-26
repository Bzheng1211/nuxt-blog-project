<template>
  <div class="blogshowcase">
    <Header :theme="theme"></Header>
    <form id="search">
      <input name="query" placeholder="Search" v-model="searchQuery">
    </form>
    <BlogPreview
      v-for="blog in filteredBlog"
      :filter-blog="searchQuery"
      :key="blog.id"
      :title="blog.title"
      :author="blog.author"
      :desc="blog.description"
      :image="blog.image"
      :imgAlt="blog.imageAlt"
      :slug="blog.slug"
    ></BlogPreview>
  </div>
</template>

<script>
export default {
  name: 'BlogPage',
  data(){
    return {
      searchQuery:"",
      theme:"First"
    }
  },
  computed:{
    filteredBlogs: function(){
      return this.blogs.filter((blog)=>{
        return blog.title.toLowerCase().match(this.searchQuery.toLowerCase())
      })
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
</style>