<template>
  <div class="calculator">
    <!-- Part 1: Simple mathematical operation -->
    <h2>Simple Math:</h2>
    <p>2 + 2 = {{ 2 + 2 }}</p>

    <!-- Part 2: String from a function using reactive data -->
    <h2>Dynamic String:</h2>
    <p>{{ getMessage() }}</p>
    
    <!-- Adding some interactivity to demonstrate reactivity -->
    <input v-model="name" placeholder="Enter your name">
    <input v-model="age" type="number" placeholder="Enter your age">
  </div>
</template>

<script>
export default {
  name: 'Calculator',
  data() {
    return {
      name: '',
      age: null
    }
  },
  methods: {
    getMessage() {
      if (!this.name || !this.age) {
        return "Please enter your name and age"
      }
      return `Hello ${this.name}, you will be ${parseInt(this.age) + 1} years old next year!`
    }
  }
}
</script>