<template>
  <div class="app">

    <h3>Создание поста</h3>
    <post-form @create="createPost"/>

    <h3>Список постов</h3>
    <post-list :posts="posts"/>

  </div>
</template>

<script>
import PostForm from "./components/PostForm";
import PostList from "./components/PostList";

export default {
  components: {
    PostForm, PostList
  },
  data() {
    return {
      posts: [
        {id: 1, title: 'Название 1', description: 'Описание поста 1'},
        {id: 2, title: 'Название 2', description: 'Описание поста 2'},
        {id: 3, title: 'Название 3', description: 'Описание поста 3'},
      ],
    }
  },
  methods: {
    createPost(post) {
      console.log(post)
      this.posts.push(post)
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
</style>
