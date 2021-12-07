<template>
    <div>
        <NuxtLink to="/todos">view</NuxtLink>
        <ul>
          <li v-for="(post, index) in posts" :key="index">
              {{ post.title }} <span><NuxtLink :to="`/posts/${post.id}/view`">view</NuxtLink></span>
          </li>
        </ul>
    </div>
</template>

<script>
export default {
  data() {
    return {
      posts: []
    }
  },
  mounted() {
     this.$axios.get('https://jsonplaceholder.typicode.com/posts').then(({data}) => {
      this.posts = data;
    })
  }
}
</script>
