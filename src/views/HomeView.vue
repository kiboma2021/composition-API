<template>
  <div class="home">
    <h1>Homepage</h1>

    <PostList :posts="posts"/>
  </div>
</template>

<script>
import { ref } from 'vue'
import PostList from '../components/PostList.vue'
// @ is an alias to /src
export default {
  name: 'HomeView',
  components: {PostList},
  setup(){
    const posts = ref([
      {title: 'Welcome to the blog', body: 'Lorem ipsum dolor sit amet, consectetur', id: 1},
      {title: 'Top 5 Python and Django Tips', body: 'Lorem ipsum dolor sit amet, consectetur', id: 2}
    ])
    return { posts }
  }

}
</script>
