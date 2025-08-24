<template>
  <div class="w-1/2 mx-auto p-4">
    <div class="p-4 bg-white border border-gray-200">
      <div class=mb-4>
        <input type="text" v-model="post.title" placeholder="title" class="border-gray-200 p-4 w-full">
      </div>
      <div class="mb-4">
         <textarea placeholder="content" v-model="post.content" class="border-gray-200 p-4 w-full"></textarea>
      </div>
      <div>
        <a @click.prevent="storePost" class="inline-block px-3 py-2 bg-sky-600 border border-sky-700 text-white">ADD POST</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Our App',

  data() {
    return {
      post:{}
    }
  },
  methods: {
   storePost() {
    console.log(this.post);

   }
  }
}
</script>

<style>

</style>
