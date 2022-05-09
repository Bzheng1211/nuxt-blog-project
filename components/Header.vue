<template>
    <div class="head">
        <h2 class="name">Fierfud</h2>
        <section class="buttons">
            <nuxt-link to="/">Home</nuxt-link>
            <nuxt-link to="/blogs">Blogs</nuxt-link>
            <nuxt-link to="/admin">Log In</nuxt-link>
        </section>
    </div>
</template>

<script>
    export default {
        name:"Header",
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