<template>
    <div class="slugBody">
        <div class="head">
        <h2 class="name">Fierfud</h2>
        <button class="button 2"><nuxt-link to="/"><h3>Home</h3></nuxt-link></button>
        <button class="button 1" @click="changeTheme"><h3>Theme</h3></button>
        <button class="button 3"><nuxt-link to="/blogs"><h3>Blogs</h3></nuxt-link></button>
        <button class="button 3"><nuxt-link to="/admin/#/"><h3>Create Blog</h3></nuxt-link></button>
        </div>
        <h2>{{article.title}}</h2>
        <img :src="article.image" :alt="article.imageAlt">
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
    .slugBody{
        font-family: 'Titillium Web', sans-serif;
    }
    .head{
        display: grid;
        font-family: 'Titillium Web', sans-serif;
        height: 15%;
        gap: 1rem;
        grid-template-columns: 5fr repeat(4, 1fr);
    }
    .button{
        color: var(--quarternary);
        border: none;
        background-color: var(--primary);

    }
    .name{
        color: var(--tertiary);
        font-size: var(--h2);
    }
    a:link {
        color: var(--quarternary);
        text-decoration: none;
    }
    a:visited {
        color: var(--quarternary);
        text-decoration: none;
    }
</style>