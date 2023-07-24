<script setup lang="ts">
import { ref } from "vue";

const props = defineProps({
  title: {
    type: String,
    reqired: true,
  },
  large: {
    type: Boolean,
    required: true,
  },
  arrow: {
    type: Boolean,
    default: false,
  },
  multi: {
    type: Boolean,
    default: false,
  },
});

const list = ref(false);

const emit = defineEmits(["toggle"]);

function toggle() {
  if (props.large) {
    emit("toggle", props.title);
  } else {
    list.value = !list.value;
    emit("toggle", props.title);
  }
}
</script>
<template>
  <div class="relative">
    <div class="p-4">
      <button
        @click="toggle"
        class="animate-[fadeIn_ease-in-out_300ms] flex items-center hover:text-blue-600 hover:underline text-[#636363]"
        :class="[
          list ? 'text-blue-600' : '',
          large ? 'text-2xl w-full' : 'text-sm',
        ]"
      >
        <p class="whitespace-nowrap">
          {{ props.title }}
        </p>
        <div :class="large ? 'flex justify-end w-full' : ''">
          <svg
            aria-hidden="true"
            fill="none"
            focusable="false"
            height="8"
            viewBox="0 0 20 20"
            width="8"
            class="ml-2"
            :class="[
              list ? 'rotate-180' : '',
              large ? '-rotate-90 w-3.5 h-3.5' : '',
            ]"
            id="cds-react-aria-16"
          >
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M10 14.293L1.354 5.646l-.708.708L10 15.707l9.354-9.353-.707-.708L10 14.293z"
              fill="currentColor"
            ></path>
          </svg>
        </div>
      </button>
    </div>
    <div
      class="absolute left-1/2 -translate-x-1/2 list-none flex-col items-center justify-center bg-white border border-gray-200 gap-4 py-4 rounded z-20 w-fit"
      :class="list && multi ? 'flex' : 'hidden'"
    >
      <a class="hover:text-blue-600 hover:underline text-[#636363] px-8">
        campus
      </a>
      <a class="hover:text-blue-600 hover:underline text-[#636363] px-8">
        campus
      </a>
      <a class="hover:text-blue-600 hover:underline text-[#636363] px-8">
        campus
      </a>
      <a class="hover:text-blue-600 hover:underline text-[#636363] px-8">
        campus
      </a>
    </div>
    <div
      v-if="list && multi"
      @click="toggle"
      class="fixed w-full h-full top-0 right-0 z-10"
    ></div>
  </div>
</template>
