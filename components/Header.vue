<template>
    <div class="head" :class="theme==='Second'?'First':'Second'">
        <h2 class="name">Fierfud</h2>
        <section class="buttons">
            <button @click="changeTheme">Change theme</button>
            <nuxt-link to="/">Home</nuxt-link>
            <nuxt-link to="/blogs">Blogs</nuxt-link>
            <nuxt-link to="/admin">Create Blog</nuxt-link>
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
    .name{
        color: var(--white);
        flex: 50%;
    }
    .head{
        display: flex;
        height: 5%;
        width: 100%;
    }
    .btnh{
        font-size: var(--h2);

    }
</style>