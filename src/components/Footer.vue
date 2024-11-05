<template>
  <footer id="footer">
    <p>Make your burger &copy; 2024</p>

  </footer>
  
</template>

<script>
export default {
  name: 'Footer',
  data() {
    return {
      // Component-specific data
    }
  },
  props: {
    // Props passed from parent component
  },
  computed: {
    // Computed properties based on props
  },
  methods: {
    // Component-specific methods
  },
  mounted() {
    // Component-specific code on mount
  }
}
</script>
<style scoped>
#footer {
  background-color: #f8f9fa;
  padding: 1rem;
  text-align: center;
  position: fixed;
  bottom: 0;
  width: 100%;
  left: 0;
  right: 0;
  z-index: 1000;
  color: #555;
  border-top: 1px solid #e9ecef;
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  transition: background-color 0.3s ease-in-out;
}
</style>