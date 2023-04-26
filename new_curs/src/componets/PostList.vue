<template>
    <div>
        <h3>Список фильмов</h3>
        <post-item
        v-for="post in posts" 
        :post="post"
        v-on:addmark="addmrk(id,post)"
        />
    </div>
    
</template>

<script>
import PostItem from "@/componets/PostItem"
export default{
    components:{PostItem},
    props:{
        posts:{
            type:Array, 
            required: true
        },
        
    },
    methods:{
        addmrk(mark , post){
        console.log("add mark and id" , mark)
        console.log("add mark" ,id)
    }
    }
    
}
</script>
<style scoped>



</style>