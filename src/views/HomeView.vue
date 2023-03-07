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
// @ is an alias to /src
export default {
  name: "HomeView",
  components: { PostList },
  setup() {
    const posts = ref([]);
    const error = ref(null);
    const showPosts = ref(true);

    const load = async () => {
      try {
        let data = await fetch("http://localhost:3000/posts");
        if (!data.ok) {
          throw Error("No data available");
        }
        posts.value = await data.json();
      } catch (err) {
        error.value = err.message;
        console.log(error.value);
      }
    };

    load();

    return { posts, showPosts, error };
  },
};
</script>
