<template>
  <div class="w-1/2 mx-auto p-4">
    <div>Name: {{ person.name }}</div>
    <div>Age: {{ person.age }}</div>
  </div>
  <div>
    <span>Click</span>
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
    sayOne() {
     console.log(11111111111111122222222222222)
    }
  }
}
</script>

<style>

</style>
