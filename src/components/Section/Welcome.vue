<script setup>
import BasicButton from '@/components/Buttons/BasicButton.vue'
import MyPicture from "@/components/Images/MyPicture.vue";
</script>

<template>
  <!-- Add drapeau fr + age + autres sous la photo -->
  <section class="container-welcome">
    <div class="left">
      <div class="title">
        <div class="emoji-hi">👋</div>
        <p class="hey">Hi, my name is</p>
        <p class="name">Loïc Delplace.</p><!-- To do : typewriter animation classico-->
      </div>
      <div class="desc">
        <h3>I am learning web development</h3>
        <p>
          I’m currently forming myself in web development especially in
          <span class="bold">frontend.</span>
        </p>
        <p>I’m seeking <span class="bold">apprenticeship.</span></p>
        <BasicButton class="checkResumeBtn"><a href="../../../public/Loic-Delplace-AlternanceCV.pdf">Check out my resume</a></BasicButton>
        <!-- TODO: dl cv mobile -->
      </div>
    </div>
    <div class="right">
      <MyPicture/>
    </div>
  </section>
</template>

<style scoped lang="scss">
.bold {
  font-weight: bold;
}
.container-welcome {
  // Centering (transform -50%,-50%, position absolute etc, care gap between desc & pic)
  display: flex;
  justify-content: center;
  align-items: center;
  height: 85vh;
  width: 100%;
  position: relative;
  @media screen and (min-width: $bp-md) {
    height: 80vh;
    display:flex;
    justify-content: space-between;
    align-items: center;
  }
  .hey {
    color: $primary-color;
    font-family: $ff-mono;
    font-weight: 400;
    font-size: 1.5rem;
  }
  .name {
    font-family: $ff-mono;
    font-weight: 400;
    color: $tertiary-color;
    padding-top: 1rem;
    font-size: 3rem;
  }
  h3 {
    color: $font-text-color;
    font-family: $ff-mono;
    font-weight: 300;
    padding-bottom: 1rem;
  }
  p {
    color: $font-text-color;
    font-family: $ff-secondary;
  }
  .desc {
    margin-top: 1rem;
    .checkResumeBtn {
      margin-top: 1rem;
      margin-bottom: 1rem;
      a {
        text-decoration: none;
        color: $primary-color;
      }
    }
  }
}

.emoji-hi {
  animation: hi-animation 2.5s infinite;
  transform-origin: 70% 70%;
  display:inline-block;
  font-size: 4rem;
}

/* Animation */


@keyframes hi-animation {
  0% {
    transform: rotate(0deg);
  }
  10% {
    transform: rotate(14deg);
  }

  20% {
    transform: rotate(-8deg);
  }

  30% {
    transform: rotate(14deg);
  }

  40% {
    transform: rotate(-4deg);
  }

  50% {
    transform: rotate(10deg);
  }
  60% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(0deg);
  }
}
</style>
