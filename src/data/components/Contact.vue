<script setup>
import { themeColor, contactInfo } from "../data/items";

const heading = "Get In Touch";
const subHeading = "Far from the countries Vokalia and Consonantia";
const contactInfoHeading = "Contact Information";
const buttonSendMessage = "Send Message";
const labels = {
  firstName: "First Name",
  lastName: "Last Name",
  email: "Email Address",
  message: "Message",
};
</script>

<template>
  <div class="py-16 px-4 md:px-12 lg:px-24 bg-white" id="contact-section">
    <div class="mb-10 text-center" data-aos="fade-up" data-aos-delay="0">
      <h2 class="text-3xl md:text-4xl font-bold text-gray-800">
        {{ heading }}
      </h2>
      <p class="text-gray-600 mt-2">{{ subHeading }}</p>
    </div>
    <div class="flex flex-col lg:flex-row gap-10">
      <div class="w-full lg:w-2/3" data-aos="fade-up" data-aos-delay="100">
        <form class="space-y-6">
          <div class="flex flex-col md:flex-row gap-6">
            <div class="w-full">
              <label
                for="fname"
                class="block text-sm font-medium text-gray-700 mb-1"
                >{{ labels.firstName }}</label
              >
              <input
                type="text"
                id="fname"
                class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
              />
            </div>
            <div class="w-full">
              <label
                for="lname"
                class="block text-sm font-medium text-gray-700 mb-1"
                >{{ labels.lastName }}</label
              >
              <input
                type="text"
                id="lname"
                class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
              />
            </div>
          </div>
          <div>
            <label
              for="email"
              class="block text-sm font-medium text-gray-700 mb-1"
              >{{ labels.email }}</label
            >
            <input
              type="email"
              id="email"
              class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
            />
          </div>
          <div>
            <label
              for="message"
              class="block text-sm font-medium text-gray-700 mb-1"
              >{{ labels.message }}</label
            >
            <textarea
              id="message"
              rows="5"
              class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
            ></textarea>
          </div>
          <button
            type="submit"
            class="px-6 py-2 rounded-md text-white"
            :style="[
              { backgroundColor: themeColor },
              { borderColor: themeColor },
            ]"
          >
            {{ buttonSendMessage }}
          </button>
        </form>
      </div>
      <div class="w-full lg:w-1/3" data-aos="fade-up" data-aos-delay="200">
        <h3 class="text-xl font-semibold text-gray-800 mb-4">
          {{ contactInfoHeading }}
        </h3>
        <address class="text-gray-700 mb-4">
          📍 {{ contactInfo.address }}
        </address>
        <ul class="space-y-3 text-gray-700">
          <li>
            📞
            <a
              :href="'tel://' + contactInfo.phone1"
              class="hover:text-blue-500"
              >{{ contactInfo.phone1 }}</a
            >
          </li>
          <li>
            📞
            <a
              :href="'tel://' + contactInfo.phone2"
              class="hover:text-blue-500"
              >{{ contactInfo.phone2 }}</a
            >
          </li>
          <li>
            📧
            <a
              :href="'mailto:' + contactInfo.email"
              class="hover:text-blue-500"
              >{{ contactInfo.email }}</a
            >
          </li>
          <li>
            🌐
            <a
              :href="contactInfo.website"
              target="_blank"
              class="hover:text-blue-500"
              >{{ contactInfo.website }}</a
            >
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
