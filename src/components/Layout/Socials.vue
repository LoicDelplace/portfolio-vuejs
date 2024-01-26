<script setup>
import GithubLink from "@/components/Buttons/Links/GithubLink.vue";
import LinkedInLink from "@/components/Buttons/Links/LinkedInLink.vue";
</script>

<template>
  <div class="social-network">
      <GithubLink class="github" link="LoicDelplace"/>
      <LinkedInLink class="linkedin" link="loicdelplace"/>
  </div>
  <div class="line-frombottom">
  </div>
  <div class="line-frombottom right">

  </div>
</template>

<style scoped lang="scss">
@media screen and (max-width: $bp-md) {
  .social-network img,.github,.linkedin, .line-frombottom {
    display: none;
  }
}

.social-network {
  z-index: 100;
  position: fixed;
  bottom: 4rem;
  left: 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  img {
    width: 40px;
    height: 40px;
  }
  img:nth-child(2) {
    margin-top: 1rem;
  }
}

.line-frombottom{
  z-index: 100;
  position: fixed;
  bottom: 0;
  left: 2.1rem;
  width: 3px;
  height: 4rem;
  background-color: #8892af;
  border-radius: 10px 10px 0 0;
}

.line-frombottom.right {
  left: auto;
  right: 2.1rem;
}
</style>