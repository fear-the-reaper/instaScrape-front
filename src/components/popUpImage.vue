<template>
    <div>
      <button @click="openModal" class="button">Show comment</button>
      <div v-if="showModal" class="modal is-active">
        <div class="modal-background" @click="closeModal"></div>
        <div class="modal-content">
          <button class="modal-close is-large" aria-label="close" @click="closeModal"></button>
          <img :src="base64String" alt="Base64 Image" />
        </div>
      </div>
    </div>
</template>
  
<script setup>
  import { ref } from 'vue';
  
  const showModal = ref(false);
  
  function openModal() {
    showModal.value = true;
  }
  
  function closeModal() {
    showModal.value = false;
  }
  
  const props = defineProps({
    base64String: {
      type: String,
      required: true
    }
  });
</script>
  
<style scoped>
    .modal {
    display: flex !important;
    align-items: center;
    justify-content: center;
    }

    .modal img {
    max-height: 80vh;
    max-width: 80vw;
    }

    .modal-close {
    position: absolute;
    top: 10px;
    right: 10px;
    }
</style>
  