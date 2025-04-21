<script setup>
import { ref } from 'vue';
    import SinglePost from './SinglePost.vue';

    const posts = ref([
        {
            id: 1,
            title: 'First Post',
            body: 'This is the first post',
        },
        {
            id: 2,
            title: 'Second Post',
            body: 'This is the second post',
        },
        {
            id: 3,
            title: 'Third Post',
            body: 'This is the third post',
        },
        {
            id: 4,
            title: 'Fourth Post',
            body: 'This is the fourth post',
        }
    ])

    const updatePostData = (post) => {
        const selectedPost = posts.value.find(p => p.id === post.id)
        if(!selectedPost) {
            return;
        }
        selectedPost.title = `${selectedPost.title} - edited` 
        selectedPost.body = `${selectedPost.body} - edited`
        return selectedPost;
    }
</script>

<template>
    <SinglePost 
        v-for = "(post, key) in posts"
        :post="post"
        :key="key"
        @update-post-info="updatePostData"
      />
</template>
