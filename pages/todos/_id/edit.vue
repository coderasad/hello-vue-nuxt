<template>
    <div class="d-flex gap">
        <b-input :value="todo.title" />

        <b-btn>Save</b-btn>
    </div>
</template>

<script>
export default {
  data() {
    return {
      todo: []
    }
  },
  mounted() {
     this.$axios.get(`https://jsonplaceholder.typicode.com/todos/${this.$route.params.id}`).then(({data}) => {
      this.todo = data;
    })
  }
}
</script>
