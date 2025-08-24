<template>
  <div class="w-1/2 mx-auto p-4">
      <div>Name: {{ person.name }}</div>
      <div>Age: {{ person.age }}</div>
    <div>
      <span @click="sayOne(222222)">Click</span>
    </div>
  </div>

</template>

<script>
export default {
  name: 'Our App',

  data() {
    return {
      person: {
        name: 'John Doe',
        age: 30,
      }
    }
  },
  methods: {
    sayOne(num) {
     console.log(num)
    }
  }
}
</script>

<style>

</style>
