<script setup>

defineProps( ['link'])

</script>

<template>
  <a :href="'https://linkedin.com/in/' + link"><div class="linkedin-logo"></div></a>
</template>

<style scoped lang="scss">
.linkedin-logo {
  width: 40px;
  height: 40px;
  background-image: url('@/assets/logos/linkedin.svg');
  background-repeat: no-repeat;
  background-size: contain;
  background-position: center;
}
</style>