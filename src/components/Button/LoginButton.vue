<script setup lang="ts">
// import LoginModal from "../LoginModal.vue";
import { ref } from "vue";
const loginModal = ref(false);

const props = defineProps({
  isLarge: {
    type: Boolean,
    required: true,
  },
});
</script>
<template>
  <a
    href="https://caodang.fpt.edu.vn/"
    @click="loginModal = true"
    :class="props.isLarge ? 'px-8 py-3 text-base' : 'px-4 py-2 text-sm'"
    class="rounded font-bold text-white bg-blue-700 hover:bg-[#00419E]"
  >
    Contact
  </a>
  <!-- <LoginModal @disable="loginModal = false" :isEnabled="loginModal" /> -->
</template>
