<script setup>
import { themeColor } from "../data/items";

const heading = "Pricing";
const subHeading = "Pricing for everyone. Choose your plan now!";
const startButtonName = "Get Started";

const packages = [
  {
    name: "Free",
    price: "0",
  },
  {
    name: "Standard",
    price: "19.99",
  },
  {
    name: "Premium",
    price: "79.99",
  },
];
</script>

<template>
  <section id="pricing-section" class="bg-gray-50 py-10">
    <div class="container mx-auto px-4">
      <div class="text-center mb-12" data-aos="fade-up">
        <h2 class="text-3xl font-bold text-gray-800">{{ heading }}</h2>
        <p class="text-gray-600 mt-2">{{ subHeading }}</p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-6xl mx-auto">
        <div
          v-for="(pkg, index) in packages"
          :key="index"
          :data-aos="'fade-up'"
          :data-aos-delay="index * 100"
          :class="[
            'bg-white rounded-lg shadow-md p-8 flex flex-col justify-between border',
            index === 1
              ? 'border-blue-500 ring-2 ring-blue-300'
              : 'border-gray-200',
          ]"
        >
          <div class="mb-6">
            <h3 class="text-xl font-semibold text-gray-800 mb-2 text-center">
              {{ pkg.name }}
            </h3>
            <div
              class="text-center text-4xl font-bold"
              :style="{ color: themeColor }"
            >
              <sup class="text-lg align-top">$</sup>{{ pkg.price }}
            </div>
            <ul class="mt-6 space-y-2 text-sm text-gray-600">
              <li>✔ There live the blind texts</li>
              <li>✔ Far far away behind the word</li>
              <li>✔ Far from the countries Vokalia and Consonantia</li>
            </ul>
          </div>
          <div class="text-center">
            <a
              href="#"
              class="inline-block px-6 py-2 rounded border text-sm font-medium transition"
              :class="index === 1 ? 'text-white' : 'bg-transparent'"
              :style="
                index === 1
                  ? { backgroundColor: themeColor, borderColor: themeColor }
                  : { color: themeColor, borderColor: themeColor }
              "
            >
              {{ startButtonName }}
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
