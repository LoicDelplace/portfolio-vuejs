<script setup>

import BasicButton from "@/components/Buttons/BasicButton.vue";
import GithubLink from "@/components/Buttons/Links/GithubLink.vue";
import LinkedInLink from "@/components/Buttons/Links/LinkedInLink.vue";
</script>

<template>
  <section class="whatsnext-container">
    <div class="section-title" id="getintouch">
      <h2><span>04.</span> What's next</h2>
    </div>
    <h3>Get in touch</h3>
    <p class="whatsnext-text">I’m always looking for new opportunities, my inbox is always open. Whether you have a question or just want to say hi, I’ll try my best to answer as fast as possible. </p>
    <div class="center-component">
      <a href="mailto:loic.delplace59@gmail.com"><BasicButton>Say hello</BasicButton></a>
    </div>
    <div class="space-btn-logo">
      <GithubLink link="LoicDelplace"/>
      <LinkedInLink link="loicdelplace"/>
    </div>
</section>
</template>

<style scoped lang="scss">
.section-title{
  width:100%;
  margin-top: 2rem;
  margin-bottom: 1rem;
  h2 {
    font-size: 20px;
    font-weight: 400;
    color: $tertiary-color;
    white-space: nowrap;
    span {
      font-size: 20px;
      color: $primary-color;
    }
  }
  display:flex;
  align-items:center;
  &:after {
    @media screen and (min-width: $bp-md) {
      display: none;
    }
    content: "";
    width: 100%;
    height: 4px;
    border-radius: 10px;
    background-color: #233654;
    margin-left: 1rem;
  }
  &:before {
    @media screen and (max-width: $bp-md) {
      display: none;
    }
    content: "";
    width: 3rem;
    height: 4px;
    border-radius: 10px;
    background-color: #233654;
    margin-left: 1rem;
    margin-right: 1rem;
  }
}

h3 {
  text-align: center;
  font-size: 2rem;
}

.whatsnext-text {
  margin-top: 1rem;
  margin-bottom: 1rem;
  text-align: center;
  font-size: 0.8rem;
  line-height: 1.5;
  color: #8892AF;
}

.center-component {
  width: 100%;
  display:flex;
  justify-content:center;
  align-items: center;
  margin-bottom: 2rem;
}

.space-btn-logo {
  @media screen and (min-width: $bp-md) {
    visibility: hidden;
  }
  width: 100%;
  display:flex;
  justify-content:space-between;
  align-items: center;
  margin-bottom: 2rem;
}

</style>