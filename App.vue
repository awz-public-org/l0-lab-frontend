<template>
  <div>
    <p>{{ message }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: 'Loading...'
    };
  },
  mounted() {
    fetch('https://mocki.io/v1/44624fbb-5e73-4f5d-9f37-ec145423003e')
      .then(response => response.text())
      .then(data => {
        this.message = data;
      })
      .catch(error => {
        this.message = 'Error fetching data';
      });
  }
}
</script>

<style scoped>
/* Optional styling */
p {
  font-size: 20px;
}
</style>
