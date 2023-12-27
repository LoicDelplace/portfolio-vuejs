<script setup>
import BasicButton from "@/components/Buttons/BasicButton.vue";


const emit = defineEmits(['closeWIP']);




</script>

<template>
    <div class="workInProgress-modal">
      <div class="modal-content">
        <img src="/Logo-LD.png" alt="logo" class="logo" />
        <p>Hey there! 🚀 </p>
        <p>My website is still a work in progress. Right now, I'm focusing on the mobile version, but there's still some polishing to be done. </p>
        <p>Thanks for understanding before you explore my portfolio. 😊</p>
        <BasicButton @click="emit('closeWIP')">I understand</BasicButton>
      </div>
    </div>
</template>

<style scoped lang="scss">
.logo {
  width: 128px;
  height: 128px;
}

.workInProgress-modal {;
  position:fixed;
  left: 0;
  right: 0;
  margin-left: auto;
  margin-right: auto;
  height: 100%;
  width: 100%;
  background: rgba(11, 25, 47, 0.90);
  z-index: 200;
  padding: 2rem;
  .modal-content{
    height: 100%;
    display:flex;
    flex-direction:column;
    gap:1rem;
    justify-content: space-around;
    align-items: center;
    text-align:center;
    @media screen and (min-width: $bp-md) {
      p {
        font-size: 2rem;
      }
    }
  }
}
</style>