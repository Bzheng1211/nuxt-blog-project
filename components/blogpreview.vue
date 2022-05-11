<template>
    <div>
        <nuxt-link :to="{ name:'slug', params:{slug:slug}}">
            <h3>{{ title }}</h3>
            <p>{{desc}}</p>
            <img v-bind:src="image" v-bind:alt="imgAlt">
        </nuxt-link>
    </div>
</template>

<script>
    export default {
        name:"BlogPreview",
        props:{
            title: String,
            author: String,
            filterblog: String,
        },
        data(){
            return {
                sortBlog:"",
            }
        },
        computed:{
            filteredData(){
                const sortBlog= this.sortBlog
                const filterBlog=this.filterblog && this.filterblog.toLowerCase()
                let data=this.title
                
            }
        },
        methods: {
            sortBy(key) {
                this.sortBlog = key
            },
        }
    }

</script>

<style>

</style>