<script setup>
defineProps({
  'link': String,
  'isLinkVisible': Boolean,
  'isWip': Boolean,
});

</script>

<template>
    <a :href="link" v-if="link"><div class="project-link"></div></a>
    <a href="#" v-if="!link"><div class="project-link"></div></a>
    <p v-if="isLinkVisible && link && !isWIP" class="link-text">{{link}}</p>
    <p v-if="isWip" class="link-text">Work in Progress</p>
</template>

<style scoped lang="scss">
.project-link {
  width: 40px;
  height: 40px;
  background-image: url('@/assets/logos/extern.svg');
  background-repeat: no-repeat;
  background-size: contain;
  background-position: center;
}
.link-text{
  display:none;
  font-size: 1rem;
  @media screen and (min-width: $bp-md) {
    display: flex;
  }
}

</style>