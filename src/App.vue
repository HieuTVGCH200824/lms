<script setup lang="ts">
import LoginButton from "./components/Button/LoginButton.vue";
import FloatCardItem from "./components/FloatCardItem.vue";
import Layout from "./components/Layout.vue";
</script>

<template>
  <div class="bg-[#F5F7F8]">
    <Layout>
      <div class="flex justify-center relative">
        <div
          class="grid lg:grid-cols-2 grid-cols-1 max-lg:grid-rows-2 max-w-[1440px]"
        >
          <div class="p-16 max-lg:pb-0">
            <h1 class="text-[#373A3C] font-semibold text-6xl pb-4">
              Strengthen employability to attract more students
            </h1>
            <p class="text-lg">
              Equip students with the most in-demand skills and prepare them for
              job success.
            </p>
            <div class="py-16">
              <LoginButton isLarge></LoginButton>
            </div>
          </div>
          <div
            class="bg-center bg-cover bg-no-repeat bg-[url('./assets/c4c-homepage-hero.jpg')]"
          ></div>
        </div>

        <div
          class="max-w-[1440px] box-border mx-auto px-12 col-span-2 h-fit absolute -bottom-36"
        >
          <div
            class="flex flex-col lg:flex-row justify-center items-center bg-[#191919] rounded-lg"
          >
            <FloatCardItem
              title="76%"
              content="Students are 76% more likely to enroll in a degree program that offers industry micro-credentials"
              :isLast="false"
            ></FloatCardItem>
            <FloatCardItem
              title="88%"
              content="of employers believe that Professional Certificates strengthen a candidate’s job application"
              :isLast="false"
            ></FloatCardItem>
            <FloatCardItem
              title="90%"
              content="of students agree that a Professional Certificate will help them secure a job"
              isLast
            ></FloatCardItem>
          </div>
        </div>
      </div>
    </Layout>
  </div>
</template>
