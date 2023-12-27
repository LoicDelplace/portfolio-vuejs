<script setup>
import {ref} from 'vue'
import XpButton from "@/components/Buttons/XpButton.vue";

//Find experience in my json and get text...
import json from '@/locales/en.json';
const formation = json.experiences.Training;

//Button selection selectTab()
let selectTab = "Formation"
//Text
let xpTitle = ref('Two Year Technical Degree');
</script>

<template>
  <div class="container-experiences">
    <div class="section-title" id="experiences">
      <p><span>02.</span> Experiences</p>
    </div>
      <div class="experiences-type">
        <!-- Rendre dynamique -->
        <XpButton class="selected">Studies</XpButton>
        <XpButton>Jobs</XpButton>
        <XpButton>Others</XpButton>
      </div>
    <div class="experiences-content">
      <div class="experience" v-if="selectTab === 'Formation'">
        <p class="xp-title">Two Year Technical Degree</p>
        <p class="xp-location">@ Lycée Edmond Labbé (Highschool) - DOUAI 59500</p>
        <p class="xp-option">in Digital System IT & Network option</p>
        <p class="xp-date">09/2018 - 06/2020</p>
        <ul class="xp-content-list">
          <li class="xp-content-item">Create Windows Forms app with <span class="green">C#</span>, understand agil methods, learning to work in team to deliver a project from zero.</li>
          <li class="xp-content-item"> I learned basics of algorithms, basics of <span>C</span>, <span>C++</span> & learned C#. </li>
        </ul>
      </div>
      <div class="experience" v-if="selectTab === 'Formation'">
        <p class="xp-title">Professional Certificate in Web and Mobile Development</p>
        <p class="xp-location">@ M2I Formation - VILLENEUVE D'ASCQ</p>
        <p class="xp-option">Full Stack Web Development</p>
        <p class="xp-date">05/2023 - 01/2024</p>
        <ul class="xp-content-list">
          <li class="xp-content-item">Beginning with <span>Figma</span> to create our UI/UX Designs</li>
          <li class="xp-content-item">Learning all basics of front web development with <span>HTML</span>, <span>CSS</span>, <span>Javascript</span>.</li>
          <li class="xp-content-item">Discover my first front web framework <span>VueJS</span></li>
          <li class="xp-content-item">The second part of my training is back-end development with <span>PHP</span> and <span>SQL</span> for my database</li>
          <li class="xp-content-item">In a second time I began working with <span>Laravel</span> and learn fundamentals about this stack.</li>
          <li class="xp-content-item">I finished my training with <span>NodeJS</span> and <span>MongoDB.</span></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">

span {
  color: $primary-font-color;
}
.section-title{
  margin-top:4rem;
  width:100%;
  p {
    font-size: 20px;
    font-weight: 400;
    color: $tertiary-color;
    white-space: nowrap;
    span {
      font-size: 20px;
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


//Media screen desktop
// Font -size : title : 2rem, location : 1rem; option: 1rem; date: 0.8rem; item: 1rem et margin-bottom: 2rem;

.experiences-content {
  width:100%;
  .experience{
    margin-top:2rem;
    &:last-child{
      margin-bottom:2rem;
    }
  }
  .xp-title {
    margin-top: 1rem;
    font-size: 1rem;
    font-weight: 400;
    color: $tertiary-color;
    @media screen and (min-width: $bp-md) {
      font-size: 2rem;
    }
  }
  .xp-location {
    margin-top: 0.5rem;
    margin-bottom: 0.5rem;
    font-size: 0.5rem;
    color: $primary-color;
    @media screen and (min-width: $bp-md) {
      font-size: 1rem;
    }
  }
  .xp-option {
    font-size: 0.8rem;
    font-weight: 400;
    color: $primary-font-color;
    @media screen and (min-width: $bp-md) {
      font-size: 1rem;
    }
  }
  .xp-date {
    margin-top: 0.5rem;
    font-size: 0.6rem;
    font-weight: 400;
    color: $tertiary-font-color;
    @media screen and (min-width: $bp-md) {
      font-size: 0.8rem;
    }
  }
  .xp-content-list {
    margin-top: 1rem;
    .xp-content-item {
      list-style-image: url(@/assets/logos/list-item-marker.svg);
      font-size: 0.7rem;
      font-weight: 400;
      color: $tertiary-font-color;
      margin-bottom: 0.5rem;
      @media screen and (min-width: $bp-md) {
        font-size: 1rem;
        margin-top: 2rem;
      }
      &:last-child {
        margin-bottom: 0;
      }
    }
  }
}

.experiences-type {
  font-family: $ff-mono;
  font-weight: 400;
  width: 100%;
  height: 3rem;
  display: flex;
  align-items: center;
  gap: 2rem;
  overflow: hidden;
  overflow-x: scroll;
  white-space: nowrap;
  padding-left: 1rem;
  padding-right: 1rem;
  border-bottom: 4px solid #233654;
  &::after{
    content: "";
    width: 100%;
    height: 4px;
    margin-left: 1rem;
  }
  &::-webkit-scrollbar {
    display: none;
  }
}
</style>