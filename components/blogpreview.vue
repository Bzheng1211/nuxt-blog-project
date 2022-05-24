<template>
    <div v-if="filteredData.length">
        <div v-for="entry in filteredData" :key="entry">
            <div v-for="key in columns" :key="key">
                {{entry[key]}}
            </div>
        </div>
    </div>
    <p v-else>No matches found</p>
</template>

<script>
    export default {
        name:"BlogPreview",
        props:{
            // data:{
            //     title: String,
            //     author: String,
            // },
            filterblog: String,
        },
        data(){
            return {
                sortBlog:"",
            }
        },
        computed:{
            filteredData(){
                // const sortBlog = this.sortBlog
                // const filterBlog=this.filterblog && this.filterblog.toLowerCase()
                // let data=this.data
                // if (filterBlog) {
                //     data = data.filter((row) => {
                //         return Object.keys(row).some((key) => {
                //             return String(row[key]).toLowerCase().indexOf(filterBlog) > -1
                //         })
                //     })
                // }
                // if (sortBlog){
                //         data = data.slice().sort((a,b)=>{
                //         a=a[sortBlog]
                //         b=b[sortBlog]
                //     })
                // }
                // return data
            }
        },
        methods: {
            // sortBy(key) {
            //     this.sortBlog = key
            // },
        }
    }
</script>

<style scoped>

</style>