
<template>

  <div class="picture-container">
    <img src="@/assets/photo-loic.png" alt="Loic Delplace Picture"/>
  </div>
</template>

<style scoped lang="scss">

img {
  @media (max-width: $bp-md) {
    display:none;
  }
  min-width: 300px;
  min-height: 300px;
  width: 300px;
  height: 300px;
  object-fit: cover;
  border: #64ffda 1px solid;
  border-radius: 30px;
}
</style>