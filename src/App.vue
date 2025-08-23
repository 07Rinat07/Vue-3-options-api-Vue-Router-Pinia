<template>
  <div class="w-1/2 mx-auto p-4">
    <div>Name: {{ person.name }}</div>
    <div>Age: {{ person.age }}</div>
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
  }
}
</script>

<style>

</style>
