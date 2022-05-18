<template>
    <div>
        <Header
        :theme="theme"
        ></Header>
        <h2>{{article.title}}</h2>
        <nuxt-content :document="article" />
    </div>
</template>

<script>
    export default {
        async asyncData({$content,params}){
            const article = await $content('blog', params.slug).fetch()
            return{article}
        },
        data(){
            return {
                theme:"First"
            }
        }
    }
</script>

<style>

</style>