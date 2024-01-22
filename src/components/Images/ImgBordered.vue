<template>

  <div class="picture-container">
    <div class="overlay">
    </div>
      <img src="@/assets/photo-cv-loic.webp" alt="Loic Delplace Picture"/>
    <div class="picture-back-border">
    </div>
  </div>
</template>

<style scoped lang="scss">
.picture-container {
  margin: 2rem auto auto;
  position: relative;
  top: 0;
  left: 0;
  width: 200px;
  height: 200px;
  .overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(100, 255, 218, 0.3);
    z-index: 1;
  }
}

img {
  position: absolute;
  top: 0;
  left: 0;
  width: 200px;
  height: 200px;
  object-fit: cover;
}

.picture-back-border {
  position: absolute;
  top: 0;
  left: 0;
  width: 200px;
  height: 200px;
  border: 3px solid $primary-color;
  z-index: -1;
  transform: translate(20px, 15px);
}
</style>
<script setup>
</script>