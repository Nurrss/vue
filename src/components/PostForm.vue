<template>
  <form @submit.prevent>
    <input v-model="post.title" class="input" type="text" placeholder="Title" />
    <input
      v-model="post.body"
      class="input"
      type="text"
      placeholder="Description"
    />
    <button class="btn" @click="createPost">Create</button>
  </form>
</template>
<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
};
</script>
<style scoped>
.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
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
