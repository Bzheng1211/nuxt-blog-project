<template>
    <div>

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