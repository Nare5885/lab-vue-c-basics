<template>
  <div class="conditional-demo">
    <h2>Conditional Rendering Demo</h2>

    <!-- Toggle button -->
    <button @click="toggleVisibility">
      Toggle Visibility
    </button>

    <!-- Element with v-if -->
    <div v-if="isVisible" class="conditional-box">
      <h3>This element uses v-if</h3>
      <p>I only exist in the DOM when isVisible is true!</p>
    </div>

    <!-- Element with v-show -->
    <div v-show="isVisible" class="conditional-box">
      <h3>This element uses v-show</h3>
      <p>I'm always in the DOM, just hidden when isVisible is false!</p>
    </div>

    <!-- Current state display -->
    <p>Current state: {{ isVisible ? 'Visible' : 'Hidden' }}</p>
  </div>
</template>

<script>
export default {
  name: 'ConditionalDemo',
  data() {
    return {
      isVisible: true  // boolean variable to control visibility
    }
  },
  methods: {
    toggleVisibility() {
      this.isVisible = !this.isVisible
    }
  }
}
</script>

<style scoped>
.conditional-box {
  margin: 20px;
  padding: 20px;
  border: 1px solid #ccc;
  background-color: #f9f9f9;
}

button {
  padding: 10px;
  margin: 10px;
  cursor: pointer;
}
</style>