<script setup>
import Welcome from '@/components/Section/Welcome.vue'
import AboutMe from "@/components/Section/AboutMe.vue";
import Socials from "@/components/Layout/Socials.vue";
import Experiences from "@/components/Section/Experiences.vue";
import MyProjects from "@/components/Section/MyProjects.vue";
import WhatsNext from "@/components/Section/WhatsNext.vue";
import Footer from "@/components/Layout/Footer.vue";
import Header from "@/components/Layout/Header.vue";
import WorkInProgress from "@/components/WorkInProgress.vue";
import {ref} from "vue";

const WIP = ref(true)

const emit = defineEmits(['closeWIP']);

const closeWIP = () => {
  WIP.value = false;
  emit('closeWIP');
};

</script>

<template>
  <WorkInProgress v-if="WIP" @closeWIP="closeWIP"></WorkInProgress>
  <Header/>
  <main>
    <Welcome />
    <AboutMe />
    <Experiences/>
    <MyProjects/>
    <WhatsNext/>
    <Socials/>
    <Footer/>
  </main>
</template>

<style scoped lang="scss">
main {
  padding: 1rem;
}
</style>