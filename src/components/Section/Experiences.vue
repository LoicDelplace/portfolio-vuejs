<script setup>
import { computed, ref } from 'vue';
import XpButton from "@/components/Buttons/XpButton.vue";
import experiencesData from '@/locales/en.json';

const selectedTab = ref('Training');
const tabs = computed(() => Object.keys(experiencesData.experiences));
const experiences = ref(experiencesData.experiences);

const selectedExperience = computed(() => {
  return experiences.value[selectedTab.value] || [];
});

const selectTab = (tab) => {
  selectedTab.value = tab;
};

</script>

<template>
  <section class="container-experiences">
    <div class="section-title" id="experiences">
      <h2><span>02.</span> Experiences</h2>
    </div>
      <div class="experiences-type">
        <XpButton
            v-for="tab in tabs"
            :key="tab"
            :label="tab"
            @selectTab="selectTab"
            :class="{ 'selected': selectedTab === tab }"
        />
      </div>
    <div class="experiences-content">
      <div class="experience" v-for="exp in selectedExperience" :key="exp.title">
        <h3 class="xp-title">{{ exp.title }}</h3>
        <p class="xp-location">{{ exp.location }}</p>
        <p class="xp-option">{{ exp.option }}</p>
        <p class="xp-date">{{ exp.date }}</p>
        <ul class="xp-content-list">
          <li class="xp-content-item" v-for="item in exp.content" :key="item" v-html="item"></li>
          <!-- Care XSS via v-html (no input etc) -->
        </ul>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">

span {
  color: $primary-font-color;
}
.section-title{
  margin-top:4rem;
  width:100%;
  h2 {
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
      font-size: 1.5rem;
    }
  }
  .xp-location {
    margin-top: 0.5rem;
    margin-bottom: 0.5rem;
    font-size: 0.5rem;
    color: $primary-color;
    @media screen and (min-width: $bp-md) {
      font-size: 1.2rem;
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