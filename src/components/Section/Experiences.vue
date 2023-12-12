<script setup>
import {ref} from 'vue'
import XpButton from "@/components/Buttons/XpButton.vue";

//Button selection selectTab()

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
        <XpButton class="selected">Formation</XpButton>
        <XpButton>Others</XpButton>
        <XpButton>Others</XpButton>
      </div>
    <div class="experiences-content">
      <p class="xp-title">{{ xpTitle }} </p>
      <p class="xp-location">@ Lycée Edmond Labbé (Highschool) - DOUAI 59500</p>
      <p class="xp-option">in Digital System IT & Network option</p>
      <p class="xp-date">09/2018 - 06/2020</p>
      <ul class="xp-content-list">
        <li class="xp-content-item">Create Windows Forms app with <span class="green">C#</span>, understand agil methods, learning to work in team to deliver a project from zero.</li>
        <li class="xp-content-item"> I learned basics of algorithms, basics of <span>C</span>, <span>C++</span> & learned C#. </li>
      </ul>
    </div>
  </div>
</template>

<style scoped lang="scss">
.container-experiences {
  min-height: 100vh;
}
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


.experiences-content {
  width:100%;
  .xp-title {
    margin-top: 1rem;
    font-size: 1rem;
    font-weight: 400;
    color: $tertiary-color;
  }
  .xp-location {
    margin-top: 0.5rem;
    margin-bottom: 0.5rem;
    font-size: 0.5rem;
    color: $primary-color;
  }
  .xp-option {
    font-size: 0.8rem;
    font-weight: 400;
    color: $primary-font-color;
  }
  .xp-date {
    margin-top: 0.5rem;
    font-size: 0.6rem;
    font-weight: 400;
    color: $tertiary-font-color;
  }
  .xp-content-list {
    margin-top: 1rem;
    .xp-content-item {
      list-style-image: url(@/assets/logos/list-item-marker.svg);
      font-size: 0.7rem;
      font-weight: 400;
      color: $tertiary-font-color;
      margin-bottom: 0.5rem;
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