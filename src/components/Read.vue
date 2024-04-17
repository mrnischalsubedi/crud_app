<template>
  <div>
    <h2>Read Items</h2>
    <!-- Display the list of items -->
    <ul>
      <li v-for="item in items" :key="item.id">{{ item.name }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  computed: {
    ...mapState(['items']) // Connect the items state to the component
  },
  created() {
    // Fetch items from the Vuex store when the component is created
    this.fetchItems();
  },
  methods: {
    ...mapActions(['fetchItems']) // Connect the fetchItems action to the component
  }
};
</script>

<style scoped>
/* Component-specific styles */
</style>
