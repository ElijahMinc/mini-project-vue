<template>
   <form @submit.prevent>
      <h4>Create post</h4>
      <input v-bind:value="post.title" @input="post.title = $event.target.value" class="input" type="text"
         placeholder="Name" />
      <input v-bind:value="post.body" @input="post.body = $event.target.value" class="input" type="text"
         placeholder="Описание" />
      <button>Click</button>
   </form>
</template>

<script>

   export default {
      data() {
         return {
            post: {
               title: '',
               body: ''
            }
         }
      },
      methods: {
         // createPostCreate(event) {
         //    this.post.id = Date.now();
         //    //....
         // }
      }

   }
</script>

<style scoped>
   .input {
      width: 100%;
      border: 1px solid teal;
      padding: 10px 15px;
      margin-top: 10px;
   }

   button {
      margin-top: 20px;
      text-align: right;
   }
</style>