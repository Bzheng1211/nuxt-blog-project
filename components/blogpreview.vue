<template>
    <div>
        <nuxt-link :to="{ name:'slug', params:{slug:slug}}">
            <h3>{{ title }}</h3>
            <p>{{desc}}</p>
            <!-- <img src="" alt=""> -->
        </nuxt-link>
    </div>
</template>

<script>
    export default {
        name:"BlogPreview",
         
    }
</script>

<style>

</style>