<template>
    <div>
        <h1>{{}}</h1>
        
    </div>
</template>

<script>
    export default {
        async asyncData({$content,params}){
            const article = await $content('blog', params.slug).fetch()
            return{article}
        }
    }
</script>

<style>

</style>