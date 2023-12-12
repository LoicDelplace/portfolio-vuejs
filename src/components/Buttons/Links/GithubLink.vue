<script setup>

defineProps( ['link'],['logowidth'],['logoheight'],)

</script>

<template>
  <a :href="'https://github.com/' + link"><div class="github-logo"></div></a>
</template>

<style scoped lang="scss">
.github-logo {
  width: 40px;
  height: 40px;
  background-image: url('@/assets/logos/github.svg');
  background-repeat: no-repeat;
  background-size: contain;
  background-position: center;
}
</style>