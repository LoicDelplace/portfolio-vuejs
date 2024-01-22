<script setup>
import ImgBordered from "@/components/Images/ImgBordered.vue";
</script>

<template>
<section class="container-about-me">
  <div class="section-title" id="about-me">
    <h2><span class="important">01. </span>About me</h2>
  </div>
  <div class="about-me-content">
    <p>Hi there! I'm Loïc, a development enthusiast exploring various technologies beyond the web. My journey started during my studies, but life led me to bartending for four years.</p>
    <p>Ready for a change, I dived back into development with a training program in April 2023. Rediscovering my love for web development, I'm now crafting my resume website/portfolio. I'm on a quest to master <span class="important">Vue</span>, and delve into <span class="important">React</span> or <span class="important">React Native</span> for mobile app development on Android and iOS. </p>
    <p>Currently, I'm honing my skills through solo projects, experimenting with various technologies :</p>
    <ul class="list-stacks">
      <li class="list-item">Javascript</li>
      <li class="list-item">PHP</li>
      <li class="list-item">Vue.js</li>
      <li class="list-item">Laravel</li>
      <li class="list-item">Nuxt.js</li>
      <li class="list-item">Node.js</li>
    </ul>
    <ImgBordered class="mypic"/>
  </div>
</section>
</template>

<style scoped lang="scss">
.important {
  color: $primary-color;
}

.section-title{
  width:100%;
  h2 {
    font-size: 20px;
    font-weight: 400;
    color: $tertiary-color;
    white-space: nowrap;
  }
  .important {
    font-size: 20px;
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

.about-me-content {
  width: 100%;
  margin-bottom: 2rem;
  p {
    text-align:justify;
    margin-top: 2rem;
    font-size: 16px;
    font-weight: 400;
    font-family: $ff-secondary;
    color: $tertiary-color;
  }
  @media screen and (min-width: $bp-md)
  {
    p {
      text-align: center;
      font-size: 1.2em;
    }
    .mypic {
      display:none;
    }
  }
}

.list-stacks {
  margin-top: 2em;
  display:grid;
  grid-template-rows: 1fr 1fr 1fr;
  grid-template-columns: 1fr 1fr;
  gap:1em;
  .list-item {
    list-style-image: url(@/assets/logos/list-item-marker.svg);
    font-weight: 400;
    font-family: $ff-mono;
    color: $primary-color;
  //  TO DO : centrer les éléments et attention aux markers
  }
  @media screen and (min-width: $bp-md)
  {
    display:grid;
  }
}
</style>