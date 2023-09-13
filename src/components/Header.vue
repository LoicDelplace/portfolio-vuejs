<script setup>
import { ref } from 'vue'
</script>

<template>
  <header>
    <div class="wrapper">
      <img src="../../Logo-LD.png" alt="logo" class="logo" />
    </div>
  </header>
</template>

<style lang="scss" scoped>
.logo {
  width: 64px;
  height: 64px;
}

header {
  display: flex;
  height: 5rem;
  width: 100%;
  gap: 1rem;
}
</style>