<template>
  <footer class="bg-gray-100 py-16 px-4 md:px-12 lg:px-24 text-gray-700">
    <div class="flex flex-col lg:flex-row flex-wrap gap-12">
      <!-- Column 1 -->
      <div class="lg:w-1/3 w-full">
        <h3 class="text-lg font-semibold mb-4">{{ column1Heading }}</h3>
        <p class="mb-6">{{ column1Text }}</p>
        <h3 class="text-lg font-semibold mb-4">{{ connectHeading }}</h3>
        <ul class="flex gap-3">
          <li v-for="(item, index) in socialItems" :key="index">
            <a :href="item.link" class="text-xl hover:text-blue-500">
              <span :class="item.icon"></span>
            </a>
          </li>
        </ul>
      </div>

      <!-- Column 2 -->
      <div class="lg:w-1/6 w-full">
        <h3 class="text-lg font-semibold mb-4">{{ column2Heading }}</h3>
        <ul class="space-y-2">
          <li><a href="#" class="hover:text-blue-500">La Lega Stadium</a></li>
          <li><a href="#" class="hover:text-blue-500">France Building</a></li>
          <li><a href="#" class="hover:text-blue-500">22 New Homes</a></li>
          <li><a href="#" class="hover:text-blue-500">Manage Center</a></li>
          <li><a href="#" class="hover:text-blue-500">Sports Hall</a></li>
        </ul>
      </div>

      <!-- Column 3 -->
      <div class="lg:w-1/8 w-full">
        <h3 class="text-lg font-semibold mb-4">{{ column3Heading }}</h3>
        <ul class="space-y-2">
          <li><a href="#" class="hover:text-blue-500">Architect</a></li>
          <li><a href="#" class="hover:text-blue-500">Interior Design</a></li>
          <li><a href="#" class="hover:text-blue-500">Landscape Design</a></li>
          <li><a href="#" class="hover:text-blue-500">Consultancy</a></li>
        </ul>
      </div>

      <!-- Column 4 -->
      <div class="lg:w-1/4 w-full">
        <h3 class="text-lg font-semibold mb-4">{{ column4Heading }}</h3>
        <address class="not-italic mb-4">{{ contactInfo.address }}</address>
        <ul class="space-y-2">
          <li>
            <a
              :href="'tel://' + contactInfo.phone1"
              class="hover:text-blue-500"
              >{{ contactInfo.phone1 }}</a
            >
          </li>
          <li>
            <a
              :href="'tel://' + contactInfo.phone2"
              class="hover:text-blue-500"
              >{{ contactInfo.phone2 }}</a
            >
          </li>
          <li>
            <a
              :href="'mailto:' + contactInfo.email"
              class="hover:text-blue-500"
              >{{ contactInfo.email }}</a
            >
          </li>
        </ul>
      </div>
    </div>

    <div class="mt-12 text-center border-t border-gray-300 pt-6">
      <p class="text-sm">{{ copyrightText }}</p>
    </div>
  </footer>
</template>

<script setup>
import { contactInfo } from "../data/items";

const copyrightText = "Copyright 2023, All rights reserved.";
const column1Heading = "About Launch";
const column1Text =
  "Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts.";
const column2Heading = "Projects";
const column3Heading = "Services";
const column4Heading = "Contact";

const connectHeading = "Connect";

const socialItems = [
  {
    link: "https://www.instagram.com/",
    icon: "icon-instagram",
  },
  {
    link: "https://www.twitter.com/",
    icon: "icon-twitter",
  },
  {
    link: "https://www.facebook.com/",
    icon: "icon-facebook",
  },
  {
    link: "https://www.linkedin.com/",
    icon: "icon-linkedin",
  },
  {
    link: "https://www.pinterest.com/",
    icon: "icon-pinterest",
  },
];
</script>
