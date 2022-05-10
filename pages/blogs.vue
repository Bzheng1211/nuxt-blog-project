<template>
  <div>
    <!-- // 
    https://vuejs.org/examples/#grid 
    https://vuejs.org/examples/#svg
    https://vuejs.org/examples/#crud
    -->
    <form id="search">
      <input name="query" v-model="searchQuery">
    </form>
    <BlogPreview
      v-for="blogs in blog"
      :filter-blog="searchQuery"
      :key="blogs.title"
      :title="blogs.title"
      :author="blogs.author"
      :desc="blogs.description"
      :image="blogs.image"
      :imgAlt="blogs.imageAlt"
      :slug="blogs.slug"
    ></BlogPreview>
  </div>
</template>

<script>
export default {
  name: 'BlogPage',
  data(){
    return {
      searchQuery:"",
    }
  },
  async fetch(){
    this.blogs = await this.$content('blog').fetch()
  },
}
</script>

<style scoped>

</style>