<template>
  <div class="post" v-for="post in posts">
    <div><strong>Название:</strong> {{ post.title }}</div>
    <div><strong>Описание:</strong> {{ post.description }}</div>
  </div>
</template>

<script>
export default {
  name: "PostList",
  props: {
    posts: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
.post {
  width: 100%;
  border: 2px solid teal;
  padding: 15px;
  margin-top: 15px;
}
</style>