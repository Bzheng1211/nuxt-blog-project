<template>
  <div>
    <Header :theme="theme"></Header>
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

</style>