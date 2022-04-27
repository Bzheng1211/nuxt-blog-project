<template>
  <div>
    <!-- // 
    https://vuejs.org/examples/#grid 
    https://vuejs.org/examples/#svg
    https://vuejs.org/examples/#crud
    -->
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