<template>
    <div class="head" :class="theme==='Second'?'First':'Second'">
        <h2 class="name">Fierfud</h2>
        <section class="buttons">
            <button class="button 1" @click="changeTheme">Change theme</button>
            <nuxt-link class="button 2" to="/">Home</nuxt-link>
            <nuxt-link class="button 3" to="/blogs">Blogs</nuxt-link>
            <nuxt-link class="button 4" to="/admin">Create Blog</nuxt-link>
        </section>
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
        display: flex;
    }
    .button{
        font-size: var(--h3);
    }
    .name{
        color: var(--tertiary);
        font-size: var(--h2);
    }

</style>