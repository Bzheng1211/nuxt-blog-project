<template>
  <div>
    <!-- // 
    https://vuejs.org/examples/#grid 
    https://vuejs.org/examples/#svg
    https://vuejs.org/examples/#crud
    -->
    <Header :theme="theme"></Header>
    <form id="search">
      <input name="query" v-model="searchQuery">
    </form>
    <BlogPreview
      v-for="blog in blogs"
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
  async fetch(){
    this.blogs = await this.$content('blog').fetch()
  },
}
</script>

<style>

</style>