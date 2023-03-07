<template>
  <div class="home">
    <h1>Homepage</h1>
    <div v-if="error">{{ error }}</div>
    <div v-else>
      <div v-if="posts.length">
          <div v-if="showPosts">
            <PostList :posts="posts" />
          </div>
          <button @click="showPosts = !showPosts">Show posts</button>
          <button @click="posts.pop()">Delete Post</button>
        </div>
        <div v-else>
          <p>Loading ...</p>
        </div>
      </div>

  </div>
</template>

<script>
import { ref } from "vue";
import PostList from "../components/PostList.vue";
import getData from "@/compositors/getData";
// @ is an alias to /src
export default {
  name: "HomeView",
  components: { PostList },
  setup() {
    const showPosts = ref(true);
    const { posts, error, load } = getData()
    load()
    return { posts, showPosts, error };
  },
};
</script>
