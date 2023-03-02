<template>
    <div>
            <h1>{{ post.title }} </h1>
        <hr>
            <p>{{ snippet }}</p>
        <hr>
    </div>
  
</template>

<script>
import { computed } from 'vue'
export default {
    props: ['post'],
    setup(props) {
        const snippet = computed(() => {
            return props.post.body.substring(0,50)+'...'
        })
        return { snippet }
    }

}
</script>

<style>

</style>