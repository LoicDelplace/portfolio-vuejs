<script setup>

import Project from "@/components/Project.vue";
import GithubLink from "@/components/Buttons/Links/GithubLink.vue";
</script>

<template>
  <section class="container-myproject">
    <div class="section-title" id="myprojects">
      <h2><span>03.</span> My projects</h2>
    </div>
    <div class="myproject-content">
      <Project title="PHuntP:Showdown"
               img="PHPShowdown"
               desc="Originally created during my PHP module training, I decided to revisit and expand it to create something much more refined. This is my first 'complete' project since my training. Work in progress. Link coming soon!"
               stacks="VueJS, Laravel"
      ></Project>
      <div class="check-my-git">
        <GithubLink link="LoicDelplace"></GithubLink>
        <div class="check-my-git-text">
          <p>Wanna see more?</p>
          <p>Check my git.</p>
          <p class="bold"><a href="http://www.github.com/loicdelplace">@LoicDelplace</a></p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.section-title{
  width:100%;
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

.check-my-git {
  width: 100%;
  height: 100px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-radius: 10px;
  border: 1px solid $primary-color;
  padding: 1rem;
  .check-my-git-text {
    .bold {
      color: white;
      font-family: $ff-secondary;
      }
    & a {
      color: white;
      text-decoration: none;
    }
      p {
        font-size: 14px;
        font-weight: 400;
        color: $tertiary-color;
        text-align: center;
      }
  }
}

//Desktop
@media screen and (min-width: $bp-md) {
  .check-my-git {
    width: 400px;
    margin: auto;
  }
}
</style>