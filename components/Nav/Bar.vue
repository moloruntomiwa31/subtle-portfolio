<template>
  <div
    class="sticky top-0 flex items-center justify-between px-8 py-5 shadow text-black bg-white z-50"
  >
    <h2 class="uppercase font-extrabold text-xl">OluwaFemi Aderibigbe</h2>
    <nav>
      <ul class="hidden md:flex items-center justify-between">
        <li v-for="link in navLinks" :key="link.name" class="mx-4">
          <a
            :href="link.path"
            :class="[
              'uppercase nav-link',
              { 'nav-link-active': isActive(link.path) },
            ]"
          >
            {{ link.name }}
          </a>
        </li>
      </ul>
    </nav>
    <!-- hamburger -->
    <span class="md:hidden">
      <Icon
        class="hover:cursor-pointer"
        name="pajamas:hamburger"
        size="1.5rem"
        style="color: black"
        @click="toggleOverlay"
      />
    </span>
  </div>
  <!-- side overlay -->
  <div
    v-if="isOverlayOpen"
    class="fixed inset-0 bg-black bg-opacity-50 z-50 flex justify-end"
  >
    <div class="bg-white w-64 h-full shadow-lg p-6">
      <Icon
        name="maki:cross"
        size="1.5rem"
        style="color: black"
        @click="toggleOverlay"
        class="hover:cursor-pointer"
      />
      <ul class="mt-8">
        <li v-for="link in navLinks" :key="link.name" class="my-4">
          <a
            :href="link.path"
            :class="[
              'uppercase text-black nav-link',
              { 'nav-link-active': isActive(link.path) },
            ]"
          >
            {{ link.name }}
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup lang="ts">
const navLinks = [
  { name: "Home", path: "#" },
  { name: "About", path: "#about" },
  { name: "Projects", path: "#projects" },
  { name: "Contact", path: "#contact" },
];

const isOverlayOpen = ref(false);

const toggleOverlay = () => {
  isOverlayOpen.value = !isOverlayOpen.value;
};

const route = useRoute();

const isActive = (path: string) => {
  return route.hash === path;
};
</script>

<style scoped>
.nav-link {
  color: #000;
  text-decoration: none;
  transition: color 0.3s ease;
}

.nav-link:hover {
  color: #007bff;
}

.nav-link-active {
  color: #007bff;
  font-weight: bold;
}
</style>
