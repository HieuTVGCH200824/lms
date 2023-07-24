<script setup lang="ts">
import { ref } from "vue";
import NavItem from "./NavItem.vue";
import LoginButton from "./Button/LoginButton.vue";
import NavDropDown from "./NavDropDown.vue";

const isClicked = ref(false);
const campusClicked = ref({
  HaNoi: false,
  HoChiMinh: false,
  CanTho: false,
  DaNang: false,
});

const emit = defineEmits(["selectCampus"]);

function handleSelectcampus(campus: string) {
  emit("selectCampus", campus);
}

const campusArrow = ref(false);

function handleCampus(index: string) {
  if (index == "Hn") {
    window.location.href = "https://fpl1.poly.edu.vn/";
  } else if (index == "Hcm") {
    window.location.href = "https://fpl2.poly.edu.vn/";
  } else if (index == "Other") {
    window.location.href = "https://fpl3.poly.edu.vn/";
  }
  // const updatedCampusClicked = {};
  // for (const key in campusClicked.value) {
  //   // @ts-ignore
  //   updatedCampusClicked[key] = false;
  // }
  // // @ts-ignore
  // updatedCampusClicked[index] = !campusClicked.value[index];
  // // @ts-ignore
  // campusClicked.value = updatedCampusClicked;
  // console.log(campusClicked.value);
  // campusArrow.value = !campusArrow.value;
}
</script>
<template>
  <button
    @click="isClicked = !isClicked"
    class="hover:bg-[#F3F8FF] hover:text-blue-700 px-4 py-3 transition-all ease-in-out duration-300"
  >
    <div v-if="!isClicked">
      <svg
        aria-hidden="true"
        fill="none"
        focusable="false"
        height="16"
        viewBox="0 0 16 16"
        width="16"
        id="cds-react-aria-22"
        class=""
      >
        <path
          fill-rule="evenodd"
          clip-rule="evenodd"
          d="M14 9H2V7h12v2zM14 4H2V2h12v2zM14 14H2v-2h12v2z"
          fill="currentColor"
        ></path>
      </svg>
    </div>
    <div v-else="isClicked">
      <svg
        aria-hidden="true"
        fill="none"
        focusable="false"
        height="16"
        viewBox="0 0 16 16"
        width="16"
        id="cds-react-aria-23"
        class="css-0"
      >
        <path
          fill-rule="evenodd"
          clip-rule="evenodd"
          d="M13.585 14.353l-11.94-12 .71-.706 11.94 12-.71.706z"
          fill="currentColor"
        ></path>
        <path
          fill-rule="evenodd"
          clip-rule="evenodd"
          d="M14.344 2.353l-11.99 12-.708-.706 11.99-12 .708.706z"
          fill="currentColor"
        ></path>
      </svg>
    </div>
  </button>
  <div v-if="isClicked" class="fixed top-24 w-full h-full bg-white right-0">
    <div
      class="pt-6 space-y-6 transition-all ease-in-out duration-700"
      :class="isClicked ? 'opacity-100' : 'opacity-0'"
    >
      <div class="px-5">
        <div>
          <NavItem
            @toggle="handleCampus('Hn')"
            large
            title="Ha Noi"
            :arrow="campusArrow"
          />
          <div class="">
            <NavDropDown
              @select="handleSelectcampus"
              v-if="campusClicked.HaNoi"
              class="animate-[fadeIn_ease-in-out_300ms] w-full"
            />
          </div>
          <NavItem
            @toggle="handleCampus('Hcm')"
            large
            title="Ho Chi Minh"
            :arrow="campusArrow"
          />
          <div class="">
            <NavDropDown
              @select="handleSelectcampus"
              v-if="campusClicked.HoChiMinh"
              class="animate-[fadeIn_ease-in-out_300ms] w-full"
            />
          </div>
          <NavItem
            @toggle="handleCampus('Other')"
            large
            title="Da Nang"
            :arrow="campusArrow"
          />
          <div class="">
            <NavDropDown
              @select="handleSelectcampus"
              v-if="campusClicked.CanTho"
              class="animate-[fadeIn_ease-in-out_300ms] w-full"
            />
          </div>
          <NavItem
            @toggle="handleCampus('Other')"
            large
            title="Can Tho"
            :arrow="campusArrow"
          />
          <div class="">
            <NavDropDown
              @select="handleSelectcampus"
              v-if="campusClicked.DaNang"
              class="animate-[fadeIn_ease-in-out_300ms] w-full"
            />
          </div>
          <NavItem
            @toggle="handleCampus('Other')"
            large
            title="Tay Nguyen"
            :arrow="campusArrow"
          />
        </div>
      </div>
      <div class="px-4">
        <LoginButton :isLarge="false" />
      </div>
    </div>
  </div>
</template>
