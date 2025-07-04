<script setup>
import { ref } from "vue";
import mainPhoto from "../assets/images/service2.jpg";

const items = [
  {
    id: 1,
    name: "Grow Your Business",
    des: "Far far away, behind the word mountains, far from the countries Vokalia and Consonantia.",
  },
  {
    id: 2,
    name: "Build Products",
    des: "Far far away, behind the word mountains, far from the countries Vokalia and Consonantia.",
  },
  {
    id: 3,
    name: "Success Every Day",
    des: "Far far away, behind the word mountains, far from the countries Vokalia and Consonantia.",
  },
  {
    id: 4,
    name: "Bring Ideas to Life",
    des: "Far far away, behind the word mountains, far from the countries Vokalia and Consonantia.",
  },
];

const selectedIndex = ref(0);

function selectItem(index) {
  selectedIndex.value = index;
}
</script>

<template>
  <section class="bg-white py-5">
    <div class="container mx-auto px-4">
      <!-- Responsive direction -->
      <div class="flex flex-col-reverse lg:flex-row items-center gap-10">
        <!-- Gambar: di bawah (mobile), kiri (desktop) -->
        <div
          class="w-full lg:w-6/12 relative h-[300px] sm:h-[400px] lg:h-[450px] overflow-hidden rounded shadow-lg"
        >
          <transition name="fade-slide" mode="out-in">
            <img
              :key="selectedIndex"
              :src="mainPhoto"
              alt="Image"
              class="w-full h-full object-cover"
            />
          </transition>
          <span
            class="absolute top-2 left-2 bg-blue-600 text-white text-xs px-2 py-1 rounded"
          >
            {{ items[selectedIndex].id }}/{{ items.length }}
          </span>
        </div>

        <!-- Teks: di atas (mobile), kanan (desktop) -->
        <div class="w-full lg:w-6/12 space-y-4">
          <div
            v-for="(item, index) in items"
            :key="item.id"
            class="cursor-pointer p-4 border rounded hover:bg-blue-50 transition"
            :class="
              index === selectedIndex
                ? 'border-blue-500 bg-blue-50'
                : 'border-gray-300'
            "
            @click="selectItem(index)"
          >
            <h3 class="text-lg font-bold text-gray-800">{{ item.name }}</h3>
            <p class="text-sm text-gray-600">{{ item.des }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.fade-slide-enter-active,
.fade-slide-leave-active {
  transition: all 0.4s ease;
}
.fade-slide-enter-from {
  opacity: 0;
  transform: translateX(30px);
}
.fade-slide-leave-to {
  opacity: 0;
  transform: translateX(-30px);
}
</style>
