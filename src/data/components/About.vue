<script setup>
import { themeColor } from "../data/items";
import mainPhoto from "../assets/images/about.svg";

const heading = "About";
const subHeading = "About Us";
const totalMembers = "50";
const totalTeam = "20";
</script>

<template>
  <div id="about-section" class="py-1 px-4 md:px-12 lg:px-24 bg-white">
    <div class="flex flex-col lg:flex-row justify-between items-start gap-10">
      <!-- Gambar -->
      <div class="w-full lg:w-2/3" data-aos="fade-up" data-aos-delay="100">
        <img :src="mainPhoto" alt="Image" class="w-full h-auto" />
      </div>

      <!-- Konten teks -->
      <div class="w-full lg:w-1/3">
        <!-- Heading -->
        <div class="mb-6" data-aos="fade-up" data-aos-delay="0">
          <span
            class="text-sm font-semibold tracking-wide"
            :style="[{ color: themeColor }]"
          >
            {{ heading }}
          </span>
          <h2 class="text-3xl font-bold text-black mt-2">
            {{ subHeading }}
          </h2>
        </div>

        <!-- Deskripsi -->
        <div
          class="mb-6 space-y-4 text-gray-700"
          data-aos="fade-up"
          data-aos-delay="100"
        >
          <p>
            Far far away, behind the word mountains, far from the countries
            Vokalia and Consonantia, there live the blind texts. Separated they
            live in Bookmarksgrove right at the coast.
          </p>
          <p>
            Separated they
            <span class="font-semibold text-black">
              live in Bookmarksgrove right at the coast of the Semantics </span
            >, a large language ocean. A small river named Duden flows by their
            place and supplies it with the necessary regelialia.
          </p>
        </div>

        <!-- Checklist -->
        <ul
          class="list-disc list-inside text-gray-700 mb-6"
          data-aos="fade-up"
          data-aos-delay="200"
        >
          <li>There live the blind texts</li>
          <li>Far far away behind the word</li>
          <li>Their place and supplies</li>
        </ul>

        <!-- Counter -->
        <div class="grid grid-cols-2 gap-6 text-center">
          <div data-aos="fade-up" data-aos-delay="0">
            <span class="text-3xl font-bold text-black">
              <span :data-number="totalMembers">{{ totalMembers }}</span
              >M
            </span>
            <div class="text-sm text-gray-500 mt-1">Members</div>
          </div>
          <div data-aos="fade-up" data-aos-delay="100">
            <span class="text-3xl font-bold text-black">
              <span :data-number="totalTeam">{{ totalTeam }}</span>
            </span>
            <div class="text-sm text-gray-500 mt-1">Team</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
