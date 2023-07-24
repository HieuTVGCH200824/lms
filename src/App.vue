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
            <p class="text-[#373A3C] text-2xl pb-4 text-justify">
              Phòng Công nghệ thông tin xin trân trọng thông báo về việc dịch
              chuyển hệ thống. Việc dịch chuyển này là một phần cải tiến nhằm
              nâng cao hiệu suất làm việc và cung cấp môi trường làm việc, học
              tập hiệu quả hơn.
            </p>
            <br />
            <p class="font-semibold">Chi tiết dịch chuyển:</p>
            <br />
            <p class="text-justify">
              Ngày thực hiện: Ngày 24 tháng 7 năm 2023.
            </p>
            <br />
            <p clas="text-justify">
              Thời gian ảnh hưởng: Dự kiến thời gian chuyển đổi hệ thống sẽ kéo
              dài trong khoảng 12 giờ, từ 16:00 ngày 24 tháng 7 đến 12h ngày 25
              tháng 7. Trong thời gian này, một số hệ thống và dịch vụ có thể
              không hoạt động bình thường.
            </p>
            <br />
            <p class="text-justify">
              Ảnh hưởng dự kiến: Trong quá trình dịch chuyển, có thể xảy ra sự
              cố tạm thời với một số ứng dụng và dịch vụ. Chúng tôi đã lập kế
              hoạch để giảm thiểu tối đa các ảnh hưởng này và đảm bảo việc hoạt
              động trở lại sao cho nhanh chóng và ổn định nhất.
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
