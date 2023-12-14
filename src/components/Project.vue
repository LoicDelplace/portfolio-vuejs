<script setup>
import GithubLink from '@/components/Buttons/Links/GithubLink.vue';
import ProjectLink from "@/components/Buttons/Links/ProjectLink.vue";


let props = defineProps({
  'title': String,
  'desc': String,
  'link': String,
  'stacks': String,
  'side': String,
});

// Manage container position left or right
let sideStatus = "left"
if (props.side === 'right') {
  sideStatus = "right"
}


</script>

<template>
<div class="project-container" :style="{float: sideStatus}">
  <div class="overlay"></div>
  <div class="project-title">{{title}}</div>
  <div class="project-description">
    <div class="project-description-text">{{desc}}</div>
    <div class="project-description-stacks">{{stacks}}</div>
    <div class="project-description-links">
      <GithubLink/>
      <ProjectLink/>
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
  background-size: contain;
  background-position: center;
  background-repeat: no-repeat;
  border-radius: 10px;
  padding: 1rem;
  margin:2rem auto;
  border: 1px solid $tertiary-color;
  background-image: url(@/assets/previews/shoten-log-preview.png);
  .project-title {
    color: $primary-font-color;
    font-weight: bold;
  }
  .project-description {
    .project-description-text {
      margin-top: 1rem;
      margin-bottom:1rem;
      font-size: 0.55rem;
      text-shadow: 1px 1px 2px black;
      text-align: justify;
      font-weight: 700;
      color: white;
    }
    .project-description-stacks {
      margin-bottom: 1rem;
    }
    .project-description-links {
      position: absolute;
      display:flex;
      bottom: 1rem;
      left: 1rem;
      gap: 1rem;
    }
  }

  .overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(97, 250, 213, 0.3);
    pointer-events: none;
  }
  .link-github {
    position:absolute;
    bottom: 1rem;
    left: 1rem;
    width: 24px;
    height: 24px;
  }
}
</style>