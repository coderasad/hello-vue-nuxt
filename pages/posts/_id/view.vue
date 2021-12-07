<template>
    <div class="d-flex gap">
        {{ post.body }}
    </div>
</template>

<script>
export default {
  data() {
    return {
      post: []
    }
  },
  mounted() {
     this.$axios.get(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`).then(({data}) => {
      this.post = data;
    })
  }
}
</script>
