<script setup>
const emit = defineEmits(['selectTab']);
const props = defineProps(['label'])

const selectTab = () => {
  emit('selectTab', props.label )
}
</script>

<template>
  <button @click="selectTab">
    {{ label}}
  </button>
</template>

<style scoped lang="scss">
button {
  background: none;
  border:none;
  cursor:pointer;
  font-size: 1rem;
  margin-right: 1rem;
  color: $tertiary-color;
  &.selected {
    color: $primary-color;
    border-bottom: 2px solid $primary-color;
    transition: all 0.4s ease-in-out;
  }
}
</style>