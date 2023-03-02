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
      {title: 'Welcome to the blog', body: 'Cascading Style Sheets (CSS) is a stylesheet language used to describe the presentation of a document written in HTML or XML (including XML dialects such as SVG, MathML or XHTML). CSS describes how elements should be rendered on screen, on paper, in speech, or on other media.', id: 1},
      {title: 'Top 5 Python and Django Tips', body: 'Django is a high-level Python web framework that enables rapid development of secure and maintainable websites. Built by experienced developers, Django takes care of much of the hassle of web development, so you can focus on writing your app without needing to reinvent the wheel. It is free and open source, has a thriving and active community, great documentation, and many options for free and paid-for support.', id: 2}
    ])
    return { posts }
  }

}
</script>
