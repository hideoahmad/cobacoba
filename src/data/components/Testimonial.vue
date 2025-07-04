<template>
  <div
    class="bg-white py-16 px-4 md:px-12 lg:px-24 select-none"
    id="testimonials-section"
  >
    <div
      class="flex flex-col lg:flex-row justify-between items-start lg:items-start mb-10"
    >
      <!-- Text on the left -->
      <div class="w-full lg:w-1/3 mb-6 lg:mb-0">
        <span class="text-sm font-semibold text-blue-600 tracking-wide"
          >TESTIMONIALS</span
        >
        <h2
          class="text-3xl lg:text-4xl font-bold leading-tight text-black mt-2"
        >
          Our Customers<br />Feedbck
        </h2>
        <div class="flex gap-2 mt-6">
          <button
            @click="scrollLeft"
            class="w-10 h-10 bg-gray-200 rounded flex items-center justify-center"
          >
            <span>&larr;</span>
          </button>
          <button
            @click="scrollRight"
            class="w-10 h-10 bg-gray-200 rounded flex items-center justify-center"
          >
            <span>&rarr;</span>
          </button>
        </div>
      </div>

      <!-- Testimonials on the right -->
      <div class="w-full lg:w-2/3 relative">
        <div
          ref="scrollContainer"
          class="flex gap-6 overflow-x-auto scrollbar-hide cursor-grab active:cursor-grabbing"
          @mousedown="startDrag"
          @mousemove="onDrag"
          @mouseup="stopDrag"
          @mouseleave="stopDrag"
        >
          <div
            v-for="(testimonial, index) in extendedTestimonials"
            :key="index"
            class="min-w-[300px] w-[90%] md:w-[45%] lg:w-[40%] bg-white p-6 border rounded-lg shadow-sm flex-shrink-0 select-none"
          >
            <blockquote class="text-gray-700 italic mb-4">
              {{ testimonial.quote }}
            </blockquote>
            <div class="flex items-center">
              <img
                :src="testimonial.photo"
                alt="Image"
                class="w-12 h-12 rounded-full mr-3 object-cover"
              />
              <div>
                <strong class="block text-black">{{ testimonial.name }}</strong>
                <span class="text-gray-500 text-sm">{{
                  testimonial.designation
                }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed, onMounted, nextTick } from "vue";

const testimonials = [
  {
    name: "James Anderson",
    designation: "Facebook, Product Lead",
    quote:
      '"Separated they live in Bookmarksgrove right at the coast of the Semantics, a large language ocean. A small river named Duden flows by their place and supplies it with the necessary regelialia."',
    photo: "images/person_1.jpg",
  },
  {
    name: "James Anderson",
    designation: "Facebook, Product Lead",
    quote:
      '"Separated they live in Bookmarksgrove right at the coast of the Semantics, a large language ocean. A small river named Duden flows by their place and supplies it with the necessary regelialia."',
    photo: "images/person_2.jpg",
  },
  {
    name: "James Anderson",
    designation: "Facebook, Product Lead",
    quote:
      '"Separated they live in Bookmarksgrove right at the coast of the Semantics, a large language ocean. A small river named Duden flows by their place and supplies it with the necessary regelialia."',
    photo: "images/person_3.jpg",
  },
];

// Duplikat data di awal dan akhir agar loop tidak terasa
const extendedTestimonials = computed(() => {
  return [...testimonials, ...testimonials, ...testimonials];
});

const scrollContainer = ref(null);
let isDragging = false;
let startX;
let dragStartScroll;

const setInitialPosition = () => {
  // Pusatkan ke set kedua (karena kita duplikat 3x)
  const container = scrollContainer.value;
  const itemWidth = container.scrollWidth / 3;
  container.scrollLeft = itemWidth;
};

onMounted(() => {
  nextTick(() => {
    setInitialPosition();
  });
});

const startDrag = (e) => {
  isDragging = true;
  startX = e.pageX - scrollContainer.value.offsetLeft;
  dragStartScroll = scrollContainer.value.scrollLeft;
};

const onDrag = (e) => {
  if (!isDragging) return;
  e.preventDefault();
  const x = e.pageX - scrollContainer.value.offsetLeft;
  const walk = (x - startX) * 1.5;
  const container = scrollContainer.value;
  container.scrollLeft = dragStartScroll - walk;

  adjustLoop(container);
};

const stopDrag = () => {
  isDragging = false;
};

// Loop halus saat drag atau scroll kanan/kiri
const adjustLoop = (container) => {
  const totalWidth = container.scrollWidth;
  const itemWidth = totalWidth / 3;
  if (container.scrollLeft <= 0) {
    container.scrollLeft = itemWidth;
  } else if (container.scrollLeft >= itemWidth * 2) {
    container.scrollLeft = itemWidth;
  }
};

const scrollLeft = () => {
  const container = scrollContainer.value;
  container.scrollBy({ left: -container.clientWidth, behavior: "smooth" });

  // Delay pengecekan posisi untuk after scroll
  setTimeout(() => adjustLoop(container), 350);
};

const scrollRight = () => {
  const container = scrollContainer.value;
  container.scrollBy({ left: container.clientWidth, behavior: "smooth" });

  setTimeout(() => adjustLoop(container), 350);
};
</script>

<style scoped>
.scrollbar-hide::-webkit-scrollbar {
  display: none;
}
.scrollbar-hide {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
</style>
