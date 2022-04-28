<template>
  <div>
    <!-- // 
    https://vuejs.org/examples/#grid 
    https://vuejs.org/examples/#svg
    https://vuejs.org/examples/#crud
    -->
    <BlogPreview
      v-for="blogs in blog"
      :key="blogs.title"
      :title="blogs.title"
      :desc="blogs.description"
      :slug="blogs.slug"
    ></BlogPreview>
  </div>
</template>

<script>
export default {
  name: 'BlogPage',
  data(){
    return{
      blogs:[]
    }
  },
  async fetch(){
    this.blogs = await this.$content('blog').fetch()
  },
}
</script>

<style scoped>

</style>