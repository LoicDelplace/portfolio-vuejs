<script setup>

import Project from "@/components/Project.vue";
import GithubLink from "@/components/Buttons/Links/GithubLink.vue";
</script>

<template>
  <div class="container-myproject">
    <div class="section-title" id="myprojects">
      <p><span>03.</span> My projects</p>
    </div>
    <div class="myproject-content">
      <Project title="Shoten"
               img="shoten"
               desc="Shoten is a project designed to enhance the management of your manga collection. It was developed during my training as part of a collaborative effort within a three-person team. This initiative showcases my ability to contribute effectively in a group setting and my commitment to continuous learning and improvement."
               stacks="NuxtJS, Laravel"
      ></Project>
      <Project title="Uberchips"
               desc="Working on..."
               side="right"
      ></Project>
      <div class="check-my-git">
        <GithubLink link="LoicDelplace"></GithubLink>
        <div class="check-my-git-text">
          <p>Don't worry if you want to see more:</p>
          <p>Check my git.</p>
          <p class="bold">@LoicDelplace</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.section-title{
  width:100%;
  p {
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
      p {
        font-size: 14px;
        font-weight: 400;
        color: $tertiary-color;
        text-align: center;
      }
  }
}
</style>