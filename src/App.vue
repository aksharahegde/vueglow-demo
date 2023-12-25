<template>
  <section
    class="flex flex-col justify-center items-center w-full h-screen bg-gray-900"
  >
    <h1 class="mb-6 text-4xl font-bold text-gray-200">Vue Glow Demo</h1>
    <div class="flex gap-6 items-center mb-12">
      <div class="flex flex-col gap-2">
        <select v-model="colorType" id="colorType" @change="setDefaultValue">
          <option
            v-for="colorType in availableColorTypes"
            :key="colorType.value"
            :value="colorType.value"
          >
            {{ colorType.label }}
          </option>
        </select>
      </div>
      <input v-if="colorType === 'color'" v-model="color" type="color" />
      <select v-if="colorType === 'tailwind'" v-model="color" id="colorType">
        <option v-for="color in tailwindColors" :key="color" :value="color">
          {{ color }}
        </option>
      </select>
    </div>
    <GlowCapture :size="500">
      <GlowElement :color="color">
        <div
          class="glow:ring-1 glow:border-glow glow:ring-glow glow:bg-glow/[.15] border-4 border-gray-400 rounded-lg"
        >
          <div class="grid grid-cols-6 gap-2 place-items-center">
            <div class="col-span-3 p-8">
              <h2
                class="font-bold text-2xl mb-4 text-gray-200 glow:text-glow/[.8]"
              >
                Chicken Shawarma &amp; Veggies
              </h2>
              <p class="text-sm text-gray-300 glow:text-glow">
                Vitae ducimus harum earum ratione autem esse ea!
              </p>
              <button
                class="flex gap-3 items-center px-10 py-3 mt-10 mb-5 text-gray-200 whitespace-nowrap bg-gray-800 rounded-xl border transition-colors border-border hover:text-text-primary glow:text-glow glow:border-glow glow:ring glow:ring-glow"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke-width="1.5"
                  stroke="currentColor"
                  class="w-6 h-6"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    d="M15.75 10.5V6a3.75 3.75 0 1 0-7.5 0v4.5m11.356-1.993 1.263 12c.07.665-.45 1.243-1.119 1.243H4.25a1.125 1.125 0 0 1-1.12-1.243l1.264-12A1.125 1.125 0 0 1 5.513 7.5h12.974c.576 0 1.059.435 1.119 1.007ZM8.625 10.5a.375.375 0 1 1-.75 0 .375.375 0 0 1 .75 0Zm7.5 0a.375.375 0 1 1-.75 0 .375.375 0 0 1 .75 0Z"
                  />
                </svg>
                <span>Add to cart</span>
              </button>
            </div>
            <div class="col-span-3 -mt-5 -mb-10">
              <img
                class="h-[350px] object-cover object-left"
                src="https://i.ibb.co/mBg1WBp/kindpng-6728540.png"
              />
            </div>
          </div>
        </div>
      </GlowElement>
    </GlowCapture>
    <div class="mt-12 space-y-2 text-center">
      <div class="text-gray-200">
        Its a demo application for
        <a
          href="https://github.com/aksharahegde/vue-glow"
          class="underline hover:text-blue-400"
          >vue-glow</a
        >
        plugin
      </div>
      <p class="text-gray-400">
        Developed by
        <a
          href="https://github.com/aksharahegde"
          class="underline hover:text-blue-400"
          >Akshara Hegde</a
        >
      </p>
      <p class="text-gray-400">
        Follow me on
        <a
          href="https://twitter.com/akshara_dev"
          class="underline hover:text-blue-400"
          >Twitter</a
        >
      </p>
    </div>
  </section>
</template>
<script setup>
import { ref } from "vue";

const colorType = ref("color");
const color = ref("#00DC82");

const availableColorTypes = [
  {
    label: "Color",
    value: "color",
  },
  {
    label: "Tailwind",
    value: "tailwind",
  },
];

const tailwindColors = [
  "blue",
  "indigo",
  "purple",
  "pink",
  "red",
  "orange",
  "yellow",
  "green",
  "teal",
  "cyan",
  "gray",
];

const setDefaultValue = () => {
  color.value = colorType.value === "tailwind" ? "cyan" : "#00DC82";
};
</script>
