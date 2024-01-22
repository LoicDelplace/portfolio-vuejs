<script setup>
import { ref } from 'vue'
import Button from '@/components/Buttons/BasicButton.vue'
import BasicButton from "@/components/Buttons/BasicButton.vue";

let opened = ref(false);

function switchOpened() {
  opened.value = !opened.value
}
</script>

<template>
  <header>
    <div class="wrapper">
      <img src="/Logo-LD.png" alt="logo" class="logo" />
      <div class="burger" @click="switchOpened" v-if="opened === false">
        <div class="line line1"></div>
        <div class="line line2"></div>
        <div class="line line3"></div>
      </div>
      <nav class="navbar" :class="{hide : !opened }">
        <div class="close-btn" @click="switchOpened" v-if="opened === true">&times;</div>
        <ul class="navbar-items">
          <li>
            <a href="#about-me" @click="opened = false"><span class="number-nav">01.</span>About</a>
          </li>
          <li>
            <a href="#experiences" @click="opened = false"><span class="number-nav">02.</span>Experiences</a>
          </li>
          <li>
            <a href="#myprojects" @click="opened = false"><span class="number-nav">03.</span>Works</a>
          </li>
          <li>
            <a href="#getintouch" @click="opened = false"><span class="number-nav">04.</span>Get in Touch</a>
          </li>
        </ul>
        <a href="/Loic-Delplace-CV.pdf"><Button class="getResumeBtn">Resume</Button></a>
      </nav>
    </div>
  </header>
</template>

<style lang="scss" scoped>
.logo {
  width: 64px;
  height: 64px;
}

header {
  width: auto;
  gap: 1rem;
  .wrapper {
    margin-top:1rem;
    width:100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 1rem;
    @media screen and (min-width: $bp-md) {
      flex-direction: row;
      align-items: center;
      justify-content: center;
      .navbar{
        width:100%;
        display:flex;
        .navbar-items{
            display: flex;
            flex-direction: row;
            gap: 1rem;
          justify-content: space-around;
          align-items:center;
        }
      }
    }
    .burger {
      @media screen and (min-width: $bp-md) {display:none;}
      position:absolute;
      right: 2rem;
      .line {
        width: 30px;
        height: 4px;
        border-radius: 10px;
        content: "";
        background-color: $primary-color;
        margin: 6px;
      }
    }
    .navbar {
      position: fixed;
      right: 0;
      top: 0;
      background-color: $background-color;
      z-index:10;
      width: 100%;
      height: 100%;
      padding:1rem;
      @media screen and (min-width: $bp-md) {
        display:flex;
        width: 100%;
        height: 3rem;
        position: static;
      }
      .getResumeBtn {
        position: absolute;
        bottom:1rem;
        left: 1rem;
        width: calc(100% - 2rem);
        @media screen and (min-width: $bp-md) {
          position: static;
          display:flex;
          justify-content: center;
          align-items: center;
          width: 20%;
        }
      }
    }
    .navbar-items {
      margin-top: 1rem;
      display: flex;
      flex-direction: column;
      gap: 2rem;
      @media screen and (min-width: $bp-md) {
        width: 100%;
      }
      li {
        &:last-child {
        }
        list-style:none;
        a {
          text-decoration: none;
          color: $tertiary-color;
          .number-nav {
            color: $primary-color;
          }
        }
        &:hover{
          cursor: pointer;
          border-bottom: 2px solid $primary-color;
        }
        &:focus {
          border-bottom: 2px solid $primary-color;
        }
        &:active {
          border-bottom: 2px solid $primary-color;
          color: $primary-color;
        }
      }
    }
  }
}

@media screen and (min-width: $bp-md) {
  header {
  .wrapper {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
    }
  }
}

.hide {
  display:none;
}

.overlay {
  width:100vh;
  height: 100vh;
  position: fixed;
  z-index: 2;
  background-color: rgba(0, 0, 0, 0.5);
  top: 0;
  left: 0;
}

.close-btn {
  color: $primary-color;
  font-family: system-ui;
  font-size: 45px;
  font-weight: 100;
  display:flex;
  justify-content: flex-end;
}
</style>

<!-- TDL: -->
<!-- Selected nav items add class="selected" & style only on one  -->
