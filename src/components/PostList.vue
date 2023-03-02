<template>
    <h4>All posts</h4>
    <div v-for="post in posts" :key="post.id">
      {{ post.title }}
    </div>
</template>

<script>
export default {
    props: ['posts']

}
</script>

<style>

</style>