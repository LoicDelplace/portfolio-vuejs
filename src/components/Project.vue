<script setup>
import GithubLink from '@/components/Buttons/Links/GithubLink.vue';

defineProps(['title'],['desc'], ['img'])


</script>

<template>
<div class="project-container">
  <div class="overlay"></div>
  <div class="project-title">{{title}}</div>
  <div class="project-description">
    <div class="project-description-text">Shoten is a project designed to enhance the management of your manga collection. It was developed during my training as part of a collaborative effort within a three-person team. This initiative showcases my ability to contribute effectively in a group setting and my commitment to continuous learning and improvement.</div>
    <div class="project-description-stacks"></div>
    <div class="project-description-links">
      <GithubLink class="link-github"/>
    </div>
  </div>
</div>
</template>

<style scoped lang="scss">
.project-container {
  position: relative;
  display: flex;
  flex-direction: column;
  width: 100%;
  height: 250px;
  background-image: url(@/assets/previews/shoten-log-preview.png);
  background-size: contain;
  background-position: center;
  background-repeat: no-repeat;
  border-radius: 10px;
  padding: 1rem;
  margin:2rem auto;
  border: 1px solid $tertiary-color;
  .project-title {
    color: $primary-font-color;
    font-weight: bold;
    text-shadow: 0px 4px 1px rgba(0, 0, 0, 0.40);
    &:before {
      margin-bottom: 0.5rem;
      content: 'Project';
      display:block;
      font-family: $ff-mono;
    }
  }
  .project-description {
    .project-description-text {
      margin-top: 1rem;
      font-size: 0.5rem;
      text-align: justify;
      color: #f5f5f5;
      &:before {
        margin-bottom: 0.5rem;
        content: 'Description';
        display:block;
        font-family: $ff-mono;
      }
    }
  }

  .overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(100, 255, 218, 0.2);
  }
  .link-github {
    position:absolute;
    bottom: 1rem;
    left: 1rem;
  }
}
</style>