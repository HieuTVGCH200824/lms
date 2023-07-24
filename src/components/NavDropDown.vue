<script setup lang="ts">
const emit = defineEmits(["select", "close"]);
function handleSelect(param: String) {
  emit("select", param);
}

function closeDropDown() {
  emit("close");
}

const campus = [
  {
    name: "Link 1",
    id: 1,
  },
  {
    name: "Link 2",
    id: 2,
  },
  {
    name: "Link 3",
    id: 3,
  },
  {
    name: "Link 4",
    id: 4,
  },
];
</script>

<template>
  <div class="">
    <div class="bg-white">
      <div
        class="pt-12 px-12 lg:px-12 lg:mx-8 pb-16 animate-[fadeIn_ease-in-out_300ms] delay-500"
      >
        <div
          class="grid grid-cols-4 max-md:grid-cols-2 gap-10 font-semibold justify-items-start"
        >
          <div v-for="item in campus" :key="item.id">
            <button
              @click="handleSelect(item.name)"
              class="hover:text-blue-600 hover:underline text-[#636363]"
            >
              {{ item.name }}
            </button>
          </div>
        </div>
      </div>
    </div>
    <div
      @click="closeDropDown"
      class="bg-[#00255d] max-lg:hidden bg-opacity-80 fixed h-screen w-screen left-0 -z-50"
    ></div>
  </div>
</template>
