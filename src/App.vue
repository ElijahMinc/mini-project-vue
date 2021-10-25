<template>
   <div class="app">
      <post-form />
      <post-list v-bind:posts="posts" />
   </div>
</template>

<script>
   import PostForm from '@/components/PostForm'
   import PostList from '@/components/PostList'


   export default {
      components: {
         PostList,
         PostForm
      },
      data() {
         return {
            posts: [
               {
                  id: Date.now(),
                  title: 'js',
                  body: 'body',
               },
               {
                  id: Date.now(),
                  title: 'ts',
                  body: 'body',
               },
               {
                  id: Date.now(),
                  title: 'angular',
                  body: 'body',
               },
            ],
            title: '',
            body: '',
         }
      },
      methods: {
         addLike() {
            this.likes += 1
         },
         deleteLike() {
            this.likes -= 1
         },
         createPost() {
            const createPost = {
               id: Date.now(),
               title: this.title,
               body: this.body
            }
            this.posts.push(createPost)
         },
         inputTitle(event) {
            console.log(event)
            this.title = event.target.value
         }
      }
   }
</script>

<style>
   * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
   }

   .app {
      padding: 20px;
      max-width: 500px;
      margin: 0 auto;
   }
</style>