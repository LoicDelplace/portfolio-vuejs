<script setup>
import GithubLink from '@/components/Buttons/Links/GithubLink.vue';
import ProjectLink from "@/components/Buttons/Links/ProjectLink.vue";
defineProps({
  'title': String,
  'desc': String,
  'link': String,
  'stacks': String,
  'isOdd': Boolean,
});
</script>

<template>
<div class="project-container" :class="{switchSide : isOdd}">
  <div class="project-img-container">
    <img src="@/assets/previews/phuntp-preview.png" :alt="title" class="project-img"/>
  </div>
  <div class="project-content-container">
    <h4 class="project-title">{{title}}</h4>
    <p class="project-stacks">{{stacks}}</p>
    <div class="project-description">
      {{desc}}
    </div>
    <div class="project-links">
      <GithubLink link="link" v-if="link"/>
      <GithubLink link="loicdelplace" v-if="!link"/>
      <ProjectLink :is-link-visible="true" :is-wip="true"/>
    </div>
  </div>
</div>
</template>

<style scoped lang="scss">



.project-container {
  margin-bottom: 2rem;
  .project-title {
    color: #64FFDA;
    text-shadow: 0 4px 1px rgba(0, 0, 0, 0.40);
    font-size: 1.5rem;
    font-style: normal;
    font-weight: 700;
    line-height: normal;
    margin-bottom:0.5rem;
  }
  .project-stacks {
    color: #A8B2D1;
    font-size: 1rem;
    font-style: normal;
    font-weight: 300;
    line-height: normal;
    margin-bottom:1rem;
  }
  .project-description {
    margin-top: 1rem;
    margin-bottom:1rem;
    font-size: 1rem;
    text-shadow: 1px 1px 2px black;
    text-align: justify;
    font-weight: 700;
    color: #A8B2D1;
  }
  .project-links {
    display:flex;
    gap: 1rem;
    align-items:center;
  }
}

.project-img-container {
  border: 2px solid #C5C5C5;
  overflow:hidden;
  margin: 1rem 0;
  img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    aspect-ratio: auto;
    filter: blur(0.5px);
    transition: all 0.5s linear;
    zoom: 10;
    &:hover {
      filter: blur(0);
      transition: all 0.5s linear;
    }
  }
}

@media screen and (min-width: $bp-md) {
  .project-container{
    display:flex;
    gap: 1rem;
  }
  .project-img-container {
    width: 100%;
    height:400px;
  }
  .project-content-container {
    margin-top: 1rem;
    width: 100%;
    display:flex;
    flex-direction:column;
    align-items:flex-start;
    height: 400px;
    .project-stacks {
      margin-top:1rem;
    }
    .project-description {
      margin-bottom: auto;
      text-align: justify;
    }
    .project-links {
      margin-bottom:1rem;
    }
  }
}

@media screen and (min-width: $bp-md) {
  .switchSide {
    & .project-img-container {
      order:2;
    }
    .project-content-container {
      display:flex;
      flex-direction:column;
      align-items:flex-end;
      .project-description{
        text-align: right;
      }
      .project-links{
        flex-direction:row-reverse;
      }
    }
  }
}
</style>