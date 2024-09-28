<template>
    <div>
        <PostCard v-for="post in posts" :key="post.id">
            <template v-slot:header>
                <h1>{{ post.title.toUpperCase() }}</h1>
            </template>
            <template v-slot:default>
                <p>{{ post.body }}</p>
            </template>
            <template v-slot:footer>
                <hr>
                Post: {{ post.id }} | Posted by <em>User {{ post.userId }}</em>
            </template>
        </PostCard>
        
        <p><button @click="getPosts">Get Posts</button></p>      
    </div>
</template>

<script>
import axios from 'axios';
import PostCard from './PostCard.vue';


export default {
    name:"PostList",
    components: {
        PostCard,
    },
    data(){
        return{
            posts:[],
        }
    },
    methods:{
        getPosts(){
            axios.get('https://jsonplaceholder.typicode.com/posts')
            .then((response) => this.posts = response.data)
            .catch((error) => console.log(error));
        }
    }
}
</script>

<style scoped>
    button{
        width:100%;
        margin:20px 10px;
    }

</style>