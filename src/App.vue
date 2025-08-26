<template>
  <div @click="editedPost = {}" v-if="Object.keys(editedPost).length > 0" class="modal-shadow">
    <div @click.stop class="modal">
      <div class="modal-header mb-4">
        <div>
          <h3 class="text-lg">Edit post title</h3>
        </div>
      </div>
      <div class="modal-body">
        <div>
          <div class=mb-4>
            <input type="text" v-model="editedPost.title" placeholder="title" class="border border-gray-200 p-4 w-full">
          </div>
          <div class="mb-4">
            <textarea v-model="editedPost.content" placeholder="content" class="border border-gray-200 p-4 w-full"></textarea>
          </div>
          <div>
            <a @click.prevent="updatePost"
             href="#"
            class="inline-block px-3 py-2 bg-sky-600 border border-sky-700 text-white">Update Post </a>
          </div>
        </div>
      </div>


      <div class="modal-footer">

      </div>
    </div>
  </div>



  <div class="w-1/2 mx-auto p-4">
    <div class="p-4 mb-4 bg-white border border-gray-200">
      <div class=mb-4>
        <input type="text" v-model="post.title" placeholder="title" class="border border-gray-200 p-4 w-full">
      </div>
      <div class="mb-4">
         <textarea @keyup.ctrl.enter="storePost" v-model="post.content" placeholder="content" class="border border-gray-200 p-4 w-full"></textarea>
      </div>
      <div>
        <a @click.prevent="storePost" href="#" class="inline-block px-3 py-2 bg-sky-600 border border-sky-700 text-white">ADD POST</a>
      </div>
    </div>




    <div>
      <div v-for="postItem in posts" class="p-4 mb-4 bg-white border border-gray-200 flex justify-between items-center">
          <div>
             <h3 class="text-lg text-gray-800 mb-2 border-b border-gray-200">{{ postItem.title }}</h3>
             <p class="text-gray-600 break-words whitespace-pre-line"></p>
            {{ postItem.content }}
          </div>
          <div class="flex items-center">
          <svg @click="editPost(postItem)" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6 mr-2 text-emerald-600 cursor-pointer">
          <path stroke-linecap="round" stroke-linejoin="round" d="m16.862 4.487 1.687-1.688a1.875 1.875 0 1 1 2.652 2.652L6.832 19.82a4.5 4.5 0 0 1-1.897 1.13l-2.685.8.8-2.685a4.5 4.5 0 0 1 1.13-1.897L16.863 4.487Zm0 0L19.5 7.125" />
          </svg>

          <svg @click="deletePost(postItem)" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6 text-red-600 cursor-pointer ">
          <path stroke-linecap="round" stroke-linejoin="round" d="m14.74 9-.346 9m-4.788 0L9.26 9m9.968-3.21c.342.052.682.107 1.022.166m-1.022-.165L18.16 19.673a2.25 2.25 0 0 1-2.244 2.077H8.084a2.25 2.25 0 0 1-2.244-2.077L4.772 5.79m14.456 0a48.108 48.108 0 0 0-3.478-.397m-12 .562c.34-.059.68-.114 1.022-.165m0 0a48.11 48.11 0 0 1 3.478-.397m7.5 0v-.916c0-1.18-.91-2.164-2.09-2.201a51.964 51.964 0 0 0-3.32 0c-1.18.037-2.09 1.022-2.09 2.201v.916m7.5 0a48.667 48.667 0 0 0-7.5 0" />
          </svg>
          </div>
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
      posts:[],
      editedPost:{},
    }
  },
  methods: {
     storePost() {
      this.posts.unshift(this.post)
      this.post = {}
     },
     deletePost(postItem){
      const index = this.posts.indexOf(postItem)
      this.posts.splice(index,1)
     },
     editPost(postItem) {
      this.editedPost.index = this.posts.indexOf(postItem)
      this.editedPost.title = postItem.title
      this.editedPost.content = postItem.content
     },
     updatePost() {
      const post = this.posts[this.editedPost.index]
      post.title = this.editedPost.title
      post.content = this.editedPost.content
      this.editedPost = {}
     }
  },

}
</script>

<style>
  .modal-shadow {
    width: 100%;
    height: 100%;
    position: fixed;
    background: rgba(0,0,0,0.8);
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center
  }

  .modal{
    width: 50%;
    background: #fff;
    padding: 20px;
  }
</style>
