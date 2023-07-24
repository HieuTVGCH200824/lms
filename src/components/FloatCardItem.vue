<script setup lang="ts">
const props = defineProps({
  title: {
    type: String,
    reqired: true,
  },
  content: {
    type: String,
    required: true,
  },
  isLast: {
    type: Boolean,
    required: true,
  },
});
</script>
<template>
  <div
    class="py-8 mx-4 lg:px-16 lg:py-4 lg:my-8 text-white flex flex-row items-center justify-center max-lg:w-3/4"
    :class="
      props.isLast
        ? ''
        : 'max-lg:border-b-[0.8px] lg:border-r-[0.8px] border-[#636363]'
    "
  >
    <span
      class="text-[40px] max-lg:text-[32px] leading-[40px] font-semibold pr-4"
      >{{ props.title }}</span
    >
    <p class="leading-[19px] max-lg:text-[14px] break-normal">
      {{ props.content }}
    </p>
  </div>
</template>
