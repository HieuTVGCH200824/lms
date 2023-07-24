<script setup lang="ts">
const props = defineProps({
  isEnabled: {
    type: Boolean,
    required: true,
  },
});

const emit = defineEmits(["disable"]);

function disable() {
  emit("disable");
}
</script>
<template>
  <div
    v-if="props.isEnabled"
    class="fixed h-screen w-screen z-50 bg-black bg-opacity-80 flex top-0 right-0 sm:py-2"
  >
    <div
      @click.stop
      class="h-full flex max-sm:w-full justify-center bg-white sm:rounded-md m-auto"
    >
      <div class="px-6 py-4 relative">
        <button
          @click="disable"
          class="absolute right-1 w-12 h-12 rounded-full hover:bg-[#F3F8FF] flex items-center justify-center"
        >
          <svg
            aria-label="Close modal"
            class="_ufjrdd"
            viewBox="0 0 48 48"
            role="img"
            aria-labelledby="Closee40a2d15-c7e4-4cc2-8b89-382138a16fe7 Closee40a2d15-c7e4-4cc2-8b89-382138a16fe7Desc"
            xmlns="http://www.w3.org/2000/svg"
            style="fill: rgb(54, 59, 66); height: 24px; width: 24px"
          >
            <title id="Closee40a2d15-c7e4-4cc2-8b89-382138a16fe7">Close</title>
            <g
              transform="translate(-915.000000, -3440.000000)"
              role="presentation"
            >
              <polygon
                points="952.558 3449 939 3462.558 925.442 3449 924 3450.442 937.558 3463.999 924 3477.558 925.442 3479 939 3465.442 952.558 3479 954 3477.558 940.442 3463.999 954 3450.442"
              ></polygon>
            </g>
          </svg>
        </button>
        <div class="mx-4 px-4 py-3 max-w-sm flex flex-col items-center gap-8">
          <h1 class="text-[1.75rem]">Welcome back</h1>
          <div>
            <form action="" class="flex flex-col gap-3">
              <div class="flex flex-col">
                <label
                  for="username"
                  class="mb-2 text-xs leading-[18px] font-bold font-sans"
                  >Username</label
                >
                <input
                  class="border border-[#636363] focus:border-[#2A73CC] w-80 outline-none px-4 py-3"
                  placeholder="Username"
                  id="username"
                  type="text"
                />
              </div>
              <div class="flex flex-col">
                <label
                  for="password"
                  class="mb-2 text-xs leading-[18px] font-bold font-sans"
                  >Password</label
                >
                <input
                  class="border border-[#636363] focus:border-[#2A73CC] w-80 outline-none px-4 py-3"
                  placeholder="Password"
                  id="password"
                  type="password"
                />
              </div>
              <div></div>
              <button
                class="mt-3 rounded px-8 py-3 w-full font-bold text-white text-sm bg-blue-700 hover:bg-[#00419E]"
              >
                Login
              </button>
            </form>
            <div class="flex flex-row items-center justify-center">
              <hr
                class="my-6 bg-black flex items-center justify-center w-full"
              />
              <span class="px-3 font-sans text-xs text-[#616161]">or</span>
              <hr
                class="my-6 bg-black flex items-center justify-center w-full"
              />
            </div>
            <button
              class="font-sans text-sm font-bold relative py-3 px-4 border rounded border-[#1f1f1f] flex items-center justify-center w-full"
              type="button"
            >
              <svg
                aria-hidden="true"
                class="_ufjrdd"
                viewBox="0 0 24 24"
                role="img"
                aria-labelledby="Googled067d7e4-f6aa-4a3c-988f-b3a3f74360b5 Googled067d7e4-f6aa-4a3c-988f-b3a3f74360b5Desc"
                xmlns="http://www.w3.org/2000/svg"
                style="
                  fill: rgb(54, 59, 66);
                  height: 18px;
                  width: 18px;
                  left: 24px;
                  position: absolute;
                  top: 15px;
                "
              >
                <title class="font-sans text-sm font-bold">Google</title>
                <g fill="none" fill-rule="evenodd" role="presentation">
                  <path
                    d="M23.52 12.273c0-.851-.076-1.67-.218-2.455H12v4.642h6.458a5.52 5.52 0 01-2.394 3.622v3.01h3.878c2.269-2.088 3.578-5.165 3.578-8.82z"
                    fill="#4285F4"
                    fill-rule="nonzero"
                  ></path>
                  <path
                    d="M12 24c3.24 0 5.956-1.075 7.942-2.907l-3.878-3.011c-1.075.72-2.45 1.145-4.064 1.145-3.125 0-5.77-2.11-6.715-4.947H1.276v3.11A11.995 11.995 0 0012 24z"
                    fill="#34A853"
                    fill-rule="nonzero"
                  ></path>
                  <path
                    d="M5.285 14.28A7.213 7.213 0 014.91 12c0-.79.136-1.56.376-2.28V6.61H1.276A11.995 11.995 0 000 12c0 1.936.464 3.77 1.276 5.39l4.01-3.11z"
                    fill="#FBBC05"
                    fill-rule="nonzero"
                  ></path>
                  <path
                    d="M12 4.773c1.762 0 3.344.605 4.587 1.794l3.442-3.442C17.951 1.19 15.235 0 12 0 7.31 0 3.25 2.69 1.276 6.61l4.01 3.11C6.228 6.884 8.874 4.773 12 4.773z"
                    fill="#EA4335"
                    fill-rule="nonzero"
                  ></path>
                  <path d="M0 0h24v24H0z"></path>
                </g></svg
              >Continue with Google
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
