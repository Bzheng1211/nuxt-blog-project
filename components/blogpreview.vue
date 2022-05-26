<template>
    <div class="previewBody">
        <img class="previewImg" :src="{image}" :alt="{imgAlt}">
        <h3>{{title}} by: {{author}}</h3>
        <p>{{desc}}</p>
    </div>
</template>

<script>
    export default {
        name:"BlogPreview",
        props:{
            title:String,
            author:String,
            desc:String,
            image:String,
            imgAlt:String,
            filterblog: String,
        },
    }
</script>

<style>
    .previewBody{
        font-family: 'Titillium Web', sans-serif;
    }
    .previewImg{
        width: 100%;
        height: 50%;
    }
</style>