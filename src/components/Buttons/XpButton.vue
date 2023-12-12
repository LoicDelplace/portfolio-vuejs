<script setup>
</script>

<template>
  <button>
    <slot></slot>
  </button>
</template>

<style scoped lang="scss">
button {
  background: none;
  border:none;
  color: $tertiary-color;
  &.selected {
    color: $primary-color;
    border-bottom: 2px solid $primary-color;
    transition: all 0.4s ease-in-out;
  }
}
</style>