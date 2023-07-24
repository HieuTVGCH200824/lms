<script setup lang="ts">
import { ref, onBeforeMount, onBeforeUnmount } from "vue";
import HamburgerMenu from "./HamburgerMenu.vue";
import NavItem from "./NavItem.vue";
import LoginButton from "./Button/LoginButton.vue";
import NavDropDown from "./NavDropDown.vue";

const toggleCampusList = ref(false);
const oldCampusName = ref("");
const campusName = ref("campus");

const campusArrow = ref(false);
function toggleList(param: string) {
  if (param == "Campus") {
    toggleCampusList.value = !toggleCampusList.value;
    campusArrow.value = !campusArrow.value;
    // console.log(campusArrow.value);
  }

  if (param == "Hn") {
    window.location.href = "https://fpl1.poly.edu.vn/";
  } else if (param == "Hcm") {
    window.location.href = "https://fpl2.poly.edu.vn/";
  } else if (param == "Other") {
    window.location.href = "https://fpl3.poly.edu.vn/";
  }
}

function tabLink(param: string) {
  if (param == "AP") {
    window.location.href = "https://ap.poly.edu.vn/";
  } else if (param == "LMS") {
    window.location.href = "https://lms.poly.edu.vn/";
  } else if (param == "CMS") {
    window.location.href = "https://cms.poly.edu.vn/";
  }
}

const animationClass = ref("");

const showTab = ref(true);

function handleScroll() {
  const currentScroll = window.scrollY;
  if (currentScroll > 20) {
    showTab.value = false;
  } else {
    showTab.value = true;
  }
}
onBeforeMount(() => {
  window.addEventListener("scroll", handleScroll);
});

onBeforeUnmount(() => {
  window.removeEventListener("scroll", handleScroll);
});

function handleCampus(param: string) {
  oldCampusName.value = campusName.value;
  campusName.value = param;
  animationClass.value = "animate-[fadeIn_ease-in-out_300ms]";
  setTimeout(() => {
    animationClass.value = "";
  }, 400);
}
</script>
<template>
  <div class="fixed w-full z-10">
    <div
      class="bg-[#191919] text-white transition-all ease-in-out duration-200"
      :class="showTab ? 'h-10' : 'lg:h-0'"
    >
      <div v-if="showTab" class="flex flex-row lg:px-12 mx-auto max-w-[1440px]">
        <button
          @click="tabLink('AP')"
          class="px-2 mx-2 hover:bg-white hover:text-black max-md:text-sm box-border h-10 border-b-[5.6px] border-transparent focus:border-white"
        >
          <span class="max-sm:hidden"> Academic Portal</span>
          <span class="sm:hidden"> AP </span>
        </button>
        <button
          @click="tabLink('LMS')"
          class="px-2 mx-2 hover:bg-white hover:text-black max-md:text-sm box-border h-10 border-b-[5.6px] border-transparent focus:border-white"
        >
          <span class="max-sm:hidden"> Learning Management System </span>
          <span class="sm:hidden"> LMS </span>
        </button>
        <button
          @click="tabLink('CMS')"
          class="px-2 mx-2 hover:bg-white hover:text-black max-md:text-sm box-border h-10 border-b-[5.6px] border-transparent focus:border-white"
        >
          <span class="max-sm:hidden"> Course Management System </span>
          <span class="sm:hidden"> CMS </span>
        </button>
      </div>
    </div>
    <div
      class="z-10 bg-white border-b border-black border-opacity-10 h-14 lg:h-24"
    >
      <div
        class="lg:px-12 px-4 h-full lg:mx-auto flex items-center max-w-[1440px]"
      >
        <div class="lg:pr-20 pr-3 min-w-fit">
          <a href="/" class="max-h-[6rem]">
            <h1
              class="flex items-center text-2xl whitespace-nowrap text-blue-700 min-w-fit"
            >
              <img
                src="../assets/FPT_Polytechnic.png"
                class="max-h-[3.5rem] lg:max-h-[4.5rem] pr-5"
              />
              <span class="font-light">
                for
                <span :class="animationClass">
                  {{ campusName }}
                </span>
              </span>
            </h1>
          </a>
        </div>
        <div class="max-lg:hidden w-2/5 flex flex-row">
          <NavItem
            @toggle="toggleList('Hn')"
            :large="false"
            title="Ha Noi"
            :arrow="campusArrow"
          />
          <NavItem
            @toggle="toggleList('Hcm')"
            :large="false"
            title="Ho Chi Minh"
            :arrow="campusArrow"
          />
          <NavItem
            @toggle="toggleList('Other')"
            :large="false"
            title="Da Nang"
            :arrow="campusArrow"
          />
          <NavItem
            @toggle="toggleList('Other')"
            :large="false"
            title="Can Tho"
            :arrow="campusArrow"
          />
          <NavItem
            @toggle="toggleList('Other')"
            :large="false"
            title="Tay Nguyen"
            :arrow="campusArrow"
          />
        </div>
        <div class="max-lg:hidden flex justify-end w-full">
          <LoginButton :isLarge="false" />
        </div>
        <div class="lg:hidden flex justify-end w-full relative">
          <HamburgerMenu @selectCampus="handleCampus" />
        </div>
      </div>
    </div>
    <NavDropDown
      @close="toggleList('Campus')"
      @select="handleCampus"
      v-if="toggleCampusList"
      class="fixed z-10 max-lg:hidden h-3/4 top-[8.5rem] w-full"
    />
  </div>
  <div class="lg:pt-[8.5rem] pt-14">
    <slot></slot>
  </div>
  <div class="w-full mt-96 bg-white border-t border-black border-opacity-10">
    <div class="px-12 mx-auto max-w-[1440px]">
      <div class="pt-2.5 flex flex-col md:flex-row justify-around">
        <div class="px-[15px]">
          <a href="">
            <img
              src="../assets/FPT_Polytechnic.png"
              alt="logo"
              class="max-h-24"
            />
          </a>
        </div>
        <div class="px-[15px]">
          <div>
            <h1 class="text-2xl pb-4 px-4 font-medium text-[#636363]">
              THÔNG TIN LIÊN HỆ
            </h1>
            <p class="pb-4 text-sm px-4 text-[#636363]">
              Trụ sở chính Tòa nhà FPT Polytechnic, Phố Trịnh Văn Bô, Nam Từ
              Liêm, Hà Nội
            </p>
            <div class="flex flex-col md:flex-row">
              <div class="flex flex-col gap-4 px-4">
                <div>
                  <h3
                    class="pb-2 underline decoration-blue-700 text-blue-700 font-medium"
                  >
                    Cơ sở Hà Nội
                  </h3>
                  <p class="pb-8 text-sm text-[#636363]">
                    Tòa nhà FPT Polytechnic, Phố Trịnh Văn Bô, Nam Từ Liêm, Hà
                    Nội
                  </p>
                  <span class="pb-8 text-[#636363]">(024) 7300 1955 </span>
                </div>
                <div>
                  <h3
                    class="pb-2 underline decoration-blue-700 text-blue-700 font-medium"
                  >
                    Cơ sở Đà Nẵng
                  </h3>
                  <p class="pb-8 text-sm text-[#636363]">
                    Số 137 Nguyễn Thị Thập, Phường Hòa Minh, Quận Liên Chiểu,
                    TP. Đà Nẵng
                  </p>
                  <span class="pb-8 text-[#636363]"> (0236) 3710 999 </span>
                </div>
                <div>
                  <h3
                    class="pb-2 underline decoration-blue-700 text-blue-700 font-medium"
                  >
                    Cơ sở Cần Thơ
                  </h3>
                  <p class="pb-8 text-sm text-[#636363]">
                    Số 288, Nguyễn Văn Linh, phường An Khánh, quận Ninh Kiều,
                    Tp. Cần Thơ.
                  </p>
                  <span class="pb-8 text-[#636363]"> (0292) 7300 468 </span>
                </div>
                <div>
                  <h3
                    class="pb-2 underline decoration-blue-700 text-blue-700 font-medium"
                  >
                    Cơ sở Hải Phòng
                  </h3>
                  <p class="pb-8 text-sm text-[#636363]">
                    271 Lê Thánh Tông, phường Máy Chai, quận Ngô Quyền, TP Hải
                    Phòng.
                  </p>
                  <span class="pb-8 text-[#636363]"> (0915) 431 313 </span>
                </div>
              </div>
              <div class="flex flex-col gap-4 px-4">
                <div>
                  <h3
                    class="max-md:pt-4 pb-2 underline decoration-blue-700 text-blue-700 font-medium"
                  >
                    Cơ sở Hồ Chí Minh
                  </h3>
                  <p class="pb-8 text-sm text-[#636363]">
                    391A Nam Kỳ Khởi Nghĩa, Q. 3, TP. Hồ Chí Minh
                  </p>
                  <p class="pb-8 text-sm text-[#636363]">
                    778/B1 Nguyễn Kiệm, P.4, Q. Phú Nhuận, TP. Hồ Chí Minh
                  </p>
                  <p class="pb-8 text-sm text-[#636363]">
                    Toà nhà Innovation, lô 24, Công viên phần mềm Quang Trung,
                    Quận 12, Hồ Chí Minh
                  </p>
                  <span class="pb-8 text-[#636363]">
                    (028) 3526 8799 – (028) 62523434
                  </span>
                </div>
                <div>
                  <h3
                    class="pb-2 underline decoration-blue-700 text-blue-700 font-medium"
                  >
                    Cơ sở Tây Nguyên
                  </h3>
                  <p class="pb-8 text-sm text-[#636363]">
                    Số 300/6 đường Hà Huy Tập, p. Tân An, TP. Buôn Ma Thuột, Đắk
                    Lắk
                  </p>
                  <span class="pb-8 text-[#636363]"> (0262) 355 5678 </span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
