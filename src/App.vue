<script setup>
import { RouterView } from 'vue-router'
import {ref} from "vue";
const modalOpened = ref(true)

const handleCloseWIP = () => {
  modalOpened.value = false;
}
</script>

<template>
  <div :class="{ 'modal-open': modalOpened}">
    <RouterView @closeWIP="handleCloseWIP"/>
  </div>
</template>

<style scoped>
.modal-open {
  position:fixed;
  overflow:hidden;
}
</style>
