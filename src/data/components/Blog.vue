<script setup>
const heading = "Our News";
const subHeading = "Far from the countries Vokalia and Consonantia";
const blogItems = [
  {
    title: "Far far away behind the word mountains far from the countries",
    name: "James",
    date: "Jun 14, 2020",
    category: "Digital Service",
    photo: "images/person_1.jpg",
  },
  {
    title: "Far far away behind the word mountains far from the countries",
    name: "James",
    date: "Jun 14, 2020",
    category: "Digital Service",
    photo: "images/person_2.jpg",
  },
  {
    title: "Far far away behind the word mountains far from the countries",
    name: "James",
    date: "Jun 14, 2020",
    category: "Digital Service",
    photo: "images/person_3.jpg",
  },
];
</script>

<template>
  <div class="bg-gray-100 py-16 px-4 md:px-12 lg:px-24">
    <div class="text-center mb-12" data-aos="fade-up" data-aos-delay="0">
      <h2 class="text-3xl lg:text-4xl font-bold text-black">{{ heading }}</h2>
      <p class="text-gray-600 mt-2">{{ subHeading }}</p>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      <div
        v-for="(item, index) in blogItems"
        :key="index"
        class="bg-white rounded-lg shadow p-6"
        :data-aos="'fade-up'"
        :data-aos-delay="index * 100"
      >
        <div class="flex items-center mb-4">
          <img
            :src="item.photo"
            alt="Image"
            class="w-12 h-12 rounded-full mr-4 object-cover"
          />
          <div>
            <p class="text-sm font-semibold text-black">
              Posted by {{ item.name }}
            </p>
            <p class="text-xs text-gray-500">{{ item.date }}</p>
          </div>
        </div>

        <div class="mb-4">
          <p class="text-xs text-blue-600 mb-2">
            {{ item.category }}, 4 min read
          </p>
          <h3 class="text-lg font-semibold text-gray-800">
            <a href="#" class="hover:underline">{{ item.title }}</a>
          </h3>
        </div>

        <a
          href="#"
          class="inline-flex items-center text-blue-600 hover:text-blue-800"
        >
          <svg
            class="w-4 h-4"
            fill="currentColor"
            viewBox="0 0 16 16"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              d="M10.146 4.646a.5.5 0 0 1 .708 0l3 3a.5.5 0 0 1 0 .708l-3 3a.5.5 0 0 1-.708-.708L12.793 8l-2.647-2.646a.5.5 0 0 1 0-.708z"
            />
            <path
              fill-rule="evenodd"
              d="M2 8a.5.5 0 0 1 .5-.5H13a.5.5 0 0 1 0 1H2.5A.5.5 0 0 1 2 8z"
            />
          </svg>
        </a>
      </div>
    </div>
  </div>
</template>
