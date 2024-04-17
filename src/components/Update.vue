<template>
  <div>
    <h2>Update Item</h2>
    <!-- Form for updating an item -->
    <form @submit.prevent="handleSubmit">
      <input type="text" v-model="updatedName" placeholder="Enter updated item name">
      <button type="submit">Update</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      updatedName: '' // Store the updated name of the item
    };
  },
  methods: {
    handleSubmit() {
      // Dispatch an action to update the item
      this.updateItem({ id: itemId, name: this.updatedName });
      // Clear the input field after updating the item
      this.updatedName = '';
    },
    ...mapActions(['updateItem']) // Connect the updateItem action to the component
  }
};
</script>

<style scoped>
/* Component-specific styles */
</style>
