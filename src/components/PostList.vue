<script setup lang="ts"> 
    import PostService from '../services/PostService';
    import {onMounted} from 'vue';
    
    const service = new PostService();
    const posts = service.getPosts();

    onMounted(async () => {await service.fetchAll()})

     
</script>
<template>
    <h1>Posts</h1>
    <ul class="post-list">
        <li v-for="p in posts" :key="p.id">{{p.title}}</li>
    </ul>

</template>
<style scoped>
li {
    list-style: none;
    text-align: left;
}
</style>