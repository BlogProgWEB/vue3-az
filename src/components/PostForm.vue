<template>
  <form @submit.prevent>
    <input
        v-model="post.title"
        class="input"
        type="text"
    >
    <input
        v-model="post.description"
        class="input"
        type="text"
    >
    <button
        @click="createPost"
        class="btn"
    >
      Добавить
    </button>
  </form>
</template>

<script>
export default {
  name: "PostForm",
  data() {
    return {
      post: {
        title: '',
        description: '',
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit('create', this.post)
      this.post = {
        title: '',
        description: '',
      }
    }
  }
}
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}

.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

.btn {
  align-self: flex-end;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
  background: none;
  color: teal;
}
</style>