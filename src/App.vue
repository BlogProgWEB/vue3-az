<template>
  <div class="app">

    <h3>Создание поста</h3>
    <form @submit.prevent>
      <input
          v-bind:value="title"
          @input="title = $event.target.value"
          class="input"
          type="text"
      >
      <input
          v-bind:value="description"
          @input="description = $event.target.value"
          class="input"
          type="text"
      >
      <button @click="createPost" class="btn">Добавить</button>
    </form>

    <h3>Список постов</h3>
    <div class="post" v-for="post in posts">
      <div><strong>Название:</strong> {{ post.title }}</div>
      <div><strong>Описание:</strong> {{ post.description }}</div>
    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      posts: [
        {id: 1, title: 'Название 1', description: 'Описание поста 1'},
        {id: 2, title: 'Название 2', description: 'Описание поста 2'},
        {id: 3, title: 'Название 3', description: 'Описание поста 3'},
      ],
      title: '',
      description: '',
    }
  },
  methods: {
    createPost() {
      const newPost = {
        id: Date.now(),
        title: this.title,
        description: this.description,
      }
      this.posts.push(newPost);
      this.title = '';
      this.description = '';
    }
  }
}
</script>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

.app {
  margin: 10px 15px;
}

.post {
  width: 100%;
  border: 2px solid teal;
  padding: 15px;
  margin-top: 15px;
}

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
