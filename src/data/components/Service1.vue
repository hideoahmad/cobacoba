<script setup>
import { themeColor } from "../data/items";
import personPhoto from "../assets/images/person_1.jpg";
import mainPhoto from "../assets/images/service1.jpg";

const service1Heading = "Digital Services";
const service1SubHeading = "Selling Digital Services";
const service1Quote =
  '"Separated they live in Bookmarksgrove right at the coast of the Semantics, a large language ocean. A small river named Duden flows by their place and supplies it with the necessary regelialia."';
const personName = "James Anderson";
const designation = "Facebook, Product Lead";

function youtubeVideoUrl() {
  const youtubeVideoId = "FzRH7y3LbQE";
  return `https://www.youtube.com/watch?v=${youtubeVideoId}&t=9s`;
}
</script>

<template>
  <section id="features-section" class="py-20 bg-white">
    <div class="container mx-auto px-4">
      <div
        class="flex flex-col lg:flex-row lg:justify-between items-start lg:items-center gap-10"
      >
        <!-- Text Column -->
        <div class="w-full lg:w-5/12 space-y-6">
          <span
            class="text-sm font-semibold tracking-wide"
            :style="{ color: themeColor }"
            data-aos="fade-up"
            data-aos-delay="0"
          >
            {{ service1Heading }}
          </span>
          <h3
            class="text-3xl font-bold text-gray-900 mb-4"
            data-aos="fade-up"
            data-aos-delay="100"
          >
            {{ service1SubHeading }}
          </h3>
          <div
            class="text-gray-600 text-base space-y-4"
            data-aos="fade-up"
            data-aos-delay="200"
          >
            <p>
              Far far away, behind the word mountains, far from the countries
              Vokalia and Consonantia, there live the blind texts. Separated
              they live in Bookmarksgrove right at the coast
            </p>
            <ul class="list-disc list-inside">
              <li>There live the blind texts</li>
              <li>Far far away behind the word</li>
            </ul>
          </div>

          <!-- Testimonial -->
          <div
            class="bg-white p-4 rounded shadow flex gap-4 items-start"
            data-aos="fade-up"
            data-aos-delay="300"
          >
            <img
              :src="personPhoto"
              alt="Person"
              class="w-12 h-12 rounded-full object-cover"
            />
            <div>
              <blockquote class="text-sm italic text-gray-700">
                {{ service1Quote }}
              </blockquote>
              <div class="mt-2">
                <strong class="block text-gray-900">{{ personName }}</strong>
                <span class="block text-gray-500 text-sm">{{
                  designation
                }}</span>
              </div>
            </div>
          </div>
        </div>

        <div
          class="w-full lg:w-7/12 relative"
          data-aos="fade-up"
          data-aos-delay="400"
        >
          <a
            :href="youtubeVideoUrl()"
            class="relative block group"
            data-fancybox
          >
            <img
              :src="mainPhoto"
              alt="Service Image"
              class="rounded shadow-lg w-full h-auto object-cover"
            />
            <span class="absolute inset-0 flex items-center justify-center">
              <span
                class="bg-white text-blue-600 rounded-full p-4 shadow-lg transition transform group-hover:scale-110"
              >
                <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 16 16">
                  <path
                    d="M11.596 8.697l-6.363 3.692c-.54.313-1.233-.066-1.233-.697V4.308c0-.63.692-1.01 1.233-.696l6.363 3.692a.802.802 0 0 1 0 1.393z"
                  />
                </svg>
              </span>
            </span>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>
