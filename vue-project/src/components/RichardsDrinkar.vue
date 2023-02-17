<template>
  <div
    class="hero-image"
    :style="{ 'background-image': 'url(' + imageUrl + ')' }"
  ></div>
</template>

<script>
export default {
  data() {
    return {
      imageUrl: "",
    };
  },
  mounted() {
    this.imageUrl =
      "https://images.unsplash.com/photo-1582106245687-cbb466a9f07f?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1169&q=80";
  },
};
</script>

<style scoped>
.hero-image {
  width: 100%;
  height: 100vh;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
}
</style>
