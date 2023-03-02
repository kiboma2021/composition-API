<template>
    <h4>All posts</h4>
    <div v-for="post in posts" :key="post.id">

        <SinglePost :post="post" />
      
    </div>
</template>

<script>
import { onMounted, onUnmounted } from 'vue';
import SinglePost from './SinglePost.vue';
export default {
    props: ['posts'],
    components: {SinglePost},
    setup(props) {
        onMounted(() => 
            console.log("Mounted ................")
        ),
        onUnmounted(() =>
            console.log("Unmounted...")
        ),
        onUpdated(() => 
            console.log("Updated........")
        );
    }
}
</script>

<style>

</style>