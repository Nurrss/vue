<template>
  <div class="app">
    <post-form @create="createPost" />
    <post-list v-bind:posts="posts" />
  </div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";

export default {
  components: {
    PostForm,
    PostList,
  },
  data() {
    return {
      posts: [
        { id: 1, title: "Javascript", body: "About javascript" },
        { id: 2, title: "Javascript", body: "About javascript 2" },
        { id: 3, title: "Javascript", body: "About javascript 3" },
        { id: 4, title: "Javascript", body: "About javascript 4" },
      ],
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.post {
  padding: 15px;
  border: 2px solid teal;
  margin-top: 15px;
}

.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

.app {
  padding: 20px;
}

form {
  display: flex;
  flex-direction: column;
}

.btn {
  margin-top: 15px;
  padding: 10px 15px;
  align-self: flex-end;
  background: none;
  border: 1px solid teal;
}
</style>
