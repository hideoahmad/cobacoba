<script setup>
import { themeColor } from "../data/items";

const heading = "Advantage of using our products";
const subHeading = "Far from the countries Vokalia and Consonantia";

const advantages = [
  {
    name: "Grow Your Business",
    des: "Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts.",
    color: "bg-teal-300 text-teal-700",
    icon: "bi bi-app-indicator",
  },
  {
    name: "Build Products",
    des: "Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts.",
    color: "bg-yellow-300 text-yellow-800",
    icon: "bi bi-arrow-repeat",
  },
  {
    name: "Success Each Day",
    des: "Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts.",
    color: "bg-red-400 text-white",
    icon: "bi bi-briefcase",
  },
  {
    name: "Bring Ideas to Life",
    des: "Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts.",
    color: "bg-blue-500 text-white",
    icon: "bi bi-collection",
  },
];
</script>

<template>
  <section class="bg-white py-20">
    <div class="container mx-auto px-4">
      <!-- Heading -->
      <div class="text-center mb-12" data-aos="fade-up">
        <h2 class="text-3xl font-bold text-gray-800">{{ heading }}</h2>
        <p class="text-gray-500 mt-2">{{ subHeading }}</p>
      </div>

      <!-- Grid -->
      <div
        class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 text-center"
      >
        <div
          v-for="(item, index) in advantages"
          :key="index"
          class="flex flex-col items-center space-y-4"
          :data-aos="'fade-up'"
          :data-aos-delay="index * 100"
        >
          <div
            class="w-10 h-10 flex items-center justify-center rounded-xl shadow-lg"
            :class="item.color"
          >
            <i :class="item.icon" class="text-xl"></i>
          </div>
          <h3 class="text-lg font-semibold text-gray-800">{{ item.name }}</h3>
          <p class="text-gray-500 text-sm px-2">{{ item.des }}</p>
        </div>
      </div>
    </div>
  </section>
</template>
