<template>
  <div class="body">
    <h2></h2>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
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