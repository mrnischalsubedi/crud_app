<template>
  <div>
    <h2>Create Item</h2>
    <!-- Form for creating a new item -->
    <form @submit.prevent="handleSubmit">
      <input type="text" v-model="itemName" placeholder="Enter item name">
      <button type="submit">Create</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      itemName: '' // Store the name of the item to be created
    };
  },
  methods: {
    handleSubmit() {
      // Dispatch an action to create the item
      this.createItem({ name: this.itemName });
      // Clear the input field after creating the item
      this.itemName = '';
    },
    ...mapActions(['createItem']) // Connect the createItem action to the component
  }
};
</script>

<style scoped>
/* Component-specific styles */
</style>
