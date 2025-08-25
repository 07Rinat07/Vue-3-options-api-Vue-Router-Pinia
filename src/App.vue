<template>
  <div class="w-1/2 mx-auto p-4">
    <div class="p-4 mb-4 bg-white border border-gray-200">
      <div class=mb-4>
        <input type="text" v-model="post.title" placeholder="title" class="border border-gray-200 p-4 w-full">
      </div>
      <div class="mb-4">
         <textarea v-model="post.content" placeholder="content" class="border border-gray-200 p-4 w-full"></textarea>
      </div>
      <div>
        <a @click.prevent="storePost" href="#" class="inline-block px-3 py-2 bg-sky-600 border border-sky-700 text-white">ADD POST</a>
      </div>
    </div>

    <div>
        <div v-for="postItem in posts" class="p-4 mb-4 bg-white border border-gray-200">
      <h3 class="text-lg text-gray-800 mb-2 border-b border-gray-200">{{ postItem.title }}</h3>
     <p class="text-gray-600 break-words whitespace-pre-line">
  {{ postItem.content }}
</p>

    </div>
  </div>


  </div>
</template>

<script>
export default {
  name: 'OurApp',

  data() {
    return {
      post:{},
      posts:[]
    }
  },
  methods: {
   storePost() {
    this.posts.unshift(this.post)
    this.post = {}
     }
  }
}
</script>

<style>

</style>
