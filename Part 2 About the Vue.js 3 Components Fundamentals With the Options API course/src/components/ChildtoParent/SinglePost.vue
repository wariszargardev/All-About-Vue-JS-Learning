<script setup>
    
    const props = defineProps({
        post:{
            type: Object,
            required: true
        }
    });

    const emit = defineEmits(["updatePostInfo"]);

    const updatePost = (event) => {
        event.preventDefault();
        emit("updatePostInfo", props.post)
    }

</script>
<template>
    <div>
        <h2>{{ post.title }} </h2>
        <p> {{ post.body }} </p>
        <button @click.prevent="$emit('updatePostInfo', post)">Edit Post</button>
        <button @click.prevent="updatePost">Edit Post 1</button>
    </div>
</template>