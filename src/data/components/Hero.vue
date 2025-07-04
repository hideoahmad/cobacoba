<script setup>
import mainPhoto from "../assets/images/hero.svg";
import { themeColor } from "../data/items";

const buttonSeeFeature = "See Features";
const buttonPricing = "Pricing";
</script>

<template>
  <section id="home-section" class="relative py-20 bg-white">
    <!-- Dots / Dekorasi -->
    <div class="absolute top-0 left-0 w-full h-full pointer-events-none z-0">
      <div
        class="w-10 h-10 bg-blue-200 rounded-full absolute top-12 left-12 opacity-30 blur-lg animate-pulse"
      ></div>
    </div>

    <div class="relative container mx-auto px-4 z-10">
      <div class="flex flex-col-reverse lg:flex-row items-center">
        <!-- Text Section -->
        <div class="w-full lg:w-5/12 space-y-6 text-center lg:text-left">
          <h1
            class="text-3xl sm:text-4xl md:text-5xl font-bold text-gray-900 dark:text-white"
            data-aos="fade-up"
            data-aos-delay="0"
          >
            {{ heroHeading }}
          </h1>
          <div
            class="text-gray-600 dark:text-black text-base md:text-lg leading-relaxed"
            data-aos="fade-up"
            data-aos-delay="100"
          >
            <p>
              Another cool free html css template by
              <span class="bg-blue-100 text-blue-500 px-2 py-1 rounded">
                Colorlib
              </span>
              Far far away, behind the word mountains, far from the countries
              Vokalia and Consonantia, there live the blind texts. Separated
              they live in Bookmarksgrove right at the coast
            </p>
          </div>
          <div
            class="flex flex-col sm:flex-row sm:justify-center lg:justify-start gap-3"
            data-aos="fade-up"
            data-aos-delay="200"
          >
            <a
              href="#features-section"
              class="px-6 py-3 rounded text-white font-semibold text-sm shadow"
              :style="{ background: themeColor, borderColor: themeColor }"
            >
              {{ buttonSeeFeature }}
            </a>
            <a
              href="#pricing-section"
              class="px-6 py-3 rounded border font-semibold text-sm transition hover:text-white"
              :style="{ color: themeColor, borderColor: themeColor }"
              @mouseover="hoverPricing = true"
              @mouseleave="hoverPricing = false"
              :class="{ 'bg-[themeColor] text-white': false }"
            >
              {{ buttonPricing }}
            </a>
          </div>
        </div>

        <!-- Image Section -->
        <div
          class="w-full lg:w-7/12 mb-10 lg:mb-0"
          data-aos="fade-right"
          data-aos-delay="400"
        >
          <img
            :src="mainPhoto"
            alt="Hero image"
            class="w-full max-w-lg mx-auto"
          />
        </div>
      </div>
    </div>
  </section>
</template>
