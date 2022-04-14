<template>
    <div class="head">
        <h2 class="name">Fierfud</h2>
        <section class="buttons">
            <button class="btnh home">Home</button>
            <button class="btnh blogs">Blogs</button>
            <button class="btnh logIn">Log In</button>
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