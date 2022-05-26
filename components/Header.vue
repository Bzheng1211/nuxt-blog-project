<template>
    <div class="head" :class="theme==='Second'?'First':'Second'">
        <h2 class="name">Fierfud</h2>
        <button class="button 2"><nuxt-link to="/"><h3>Home</h3></nuxt-link></button>
        <button class="button 1" @click="changeTheme"><h3>Theme</h3></button>
        <button class="button 3"><nuxt-link to="/blogs"><h3>Blogs</h3></nuxt-link></button>
        <button class="button 3"><nuxt-link to="/admin"><h3>Create Blog</h3></nuxt-link></button>
    </div>
</template>

<script>
    export default {
        name:"Header",
        props:{
            theme: String,
        },
        methods:{
            changeTheme(){
                this.theme=this.theme==="Second"?"First":"Second";
            }
        },
    }
</script>

<style>
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