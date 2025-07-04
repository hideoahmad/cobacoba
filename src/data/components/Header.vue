<script setup>
import { ref } from "vue";
import { themeColor, siteName } from "../data/items";

const isMobileMenuOpen = ref(false);
</script>

<template>
  <nav class="bg-white shadow mb-5 text-black">
    <div class="container mx-auto px-4">
      <div class="flex items-center justify-between py-4">
        <!-- Logo -->
        <a href="#" class="text-xl font-bold text-gray-900 dark:text-black">
          {{ siteName }}<span class="text-blue-600">.</span>
        </a>

        <!-- Desktop Menu -->
        <ul class="hidden lg:flex space-x-6 items-center">
          <li>
            <a
              href="#home-section"
              class="text-gray-700 dark:text-black hover:text-blue-500"
              >Home</a
            >
          </li>
          <li class="relative group">
            <a
              href="#"
              class="text-gray-700 dark:text-black hover:text-blue-500"
              >Dropdown</a
            >
            <ul
              class="absolute left-0 mt-2 w-40 bg-white dark:bg-white shadow-lg hidden group-hover:block transition duration-300 ease-in-out z-10"
            >
              <li>
                <a
                  href="#testimonials-section"
                  class="block px-4 py-2 text-gray-700 dark:text-black hover:text-blue-500"
                  >Testimonials</a
                >
              </li>
              <li>
                <a
                  href="#"
                  class="block px-4 py-2 text-gray-700 dark:text-black hover:text-blue-500"
                  >Menu Two</a
                >
              </li>
              <li>
                <a
                  href="#"
                  class="block px-4 py-2 text-gray-700 dark:text-black hover:text-blue-500"
                  >Menu Three</a
                >
              </li>
            </ul>
          </li>
          <li>
            <a
              href="#features-section"
              class="text-gray-700 dark:text-black hover:text-blue-500"
              >Features</a
            >
          </li>
          <li>
            <a
              href="#pricing-section"
              class="text-gray-700 dark:text-black hover:text-blue-500"
              >Pricing</a
            >
          </li>
          <li>
            <a
              href="#about-section"
              class="text-gray-700 dark:text-black hover:text-blue-500"
              >About</a
            >
          </li>
          <li>
            <a
              href="#contact-section"
              class="text-gray-700 dark:text-black hover:text-blue-500"
              >Contact</a
            >
          </li>
        </ul>

        <!-- CTA Buttons (Desktop) -->
        <ul class="hidden lg:flex items-center space-x-4">
          <li>
            <a
              href="#"
              class="px-4 py-2 border border-blue-500 text-blue-500 rounded hover:bg-blue-50"
              >Sign in</a
            >
          </li>
          <li>
            <a
              href="#"
              class="px-4 py-2 rounded text-white"
              :style="{ backgroundColor: themeColor }"
              >Register</a
            >
          </li>
        </ul>

        <!-- Mobile Toggle Button -->
        <button
          class="lg:hidden text-gray-700 dark:text-black"
          @click="isMobileMenuOpen = !isMobileMenuOpen"
        >
          <svg
            v-if="!isMobileMenuOpen"
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M4 6h16M4 12h16M4 18h16"
            />
          </svg>
          <svg
            v-else
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M6 18L18 6M6 6l12 12"
            />
          </svg>
        </button>
      </div>

      <!-- Mobile Menu -->
      <transition name="fade">
        <div
          v-if="isMobileMenuOpen"
          class="lg:hidden mt-2 space-y-2 bg-gray-100 dark:bg-gray-800 p-4 rounded transition-all duration-300"
        >
          <ul class="space-y-2">
            <li>
              <a
                href="#home-section"
                class="block px-4 py-2 text-gray-700 dark:text-gray-200 hover:bg-blue-100 dark:hover:bg-gray-700"
                >Home</a
              >
            </li>
            <li>
              <details class="group">
                <summary
                  class="block px-4 py-2 text-gray-700 dark:text-gray-200 hover:bg-blue-100 dark:hover:bg-gray-700 cursor-pointer"
                >
                  Dropdown
                </summary>
                <ul class="pl-4 mt-1 space-y-1">
                  <li>
                    <a
                      href="#testimonials-section"
                      class="block px-4 py-2 text-gray-700 dark:text-gray-200 hover:bg-blue-100 dark:hover:bg-gray-700"
                      >Testimonials</a
                    >
                  </li>
                  <li>
                    <a
                      href="#"
                      class="block px-4 py-2 text-gray-700 dark:text-gray-200 hover:bg-blue-100 dark:hover:bg-gray-700"
                      >Menu Two</a
                    >
                  </li>
                  <li>
                    <a
                      href="#"
                      class="block px-4 py-2 text-gray-700 dark:text-gray-200 hover:bg-blue-100 dark:hover:bg-gray-700"
                      >Menu Three</a
                    >
                  </li>
                </ul>
              </details>
            </li>
            <li>
              <a
                href="#features-section"
                class="block px-4 py-2 text-gray-700 dark:text-gray-200 hover:bg-blue-100 dark:hover:bg-gray-700"
                >Features</a
              >
            </li>
            <li>
              <a
                href="#pricing-section"
                class="block px-4 py-2 text-gray-700 dark:text-gray-200 hover:bg-blue-100 dark:hover:bg-gray-700"
                >Pricing</a
              >
            </li>
            <li>
              <a
                href="#about-section"
                class="block px-4 py-2 text-gray-700 dark:text-gray-200 hover:bg-blue-100 dark:hover:bg-gray-700"
                >About</a
              >
            </li>
            <li>
              <a
                href="#contact-section"
                class="block px-4 py-2 text-gray-700 dark:text-gray-200 hover:bg-blue-100 dark:hover:bg-gray-700"
                >Contact</a
              >
            </li>
          </ul>
          <div class="pt-4 space-y-2">
            <a
              href="#"
              class="block w-full text-center border border-blue-500 text-blue-500 rounded py-2"
              >Sign in</a
            >
            <a
              href="#"
              class="block w-full text-center text-white rounded py-2"
              :style="{ backgroundColor: themeColor }"
              >Register</a
            >
          </div>
        </div>
      </transition>
    </div>
  </nav>
</template>
