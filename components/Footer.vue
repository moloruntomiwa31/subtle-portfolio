<template>
  <footer
    class="flex flex-col-reverse md:flex-row md:justify-between items-center w-full border-t px-8 py-5 shadow"
  >
    <div>
      <p class="text-gray-600">&copy;{{ presentYear }}. All rights reserved.</p>
    </div>
    <div id="contact" class="md:w-lg bg-black bg-texture p-4 rounded text-center">
      <p class="text-white text-lg font-semibold">Get In Touch</p>
      <div class="flex flex-col justify-center items-center space-y-3">
        <p class="text-lg text-gray-300 mt-4 max-w-2xl">
          I'm currently open to new opportunities. If you'd like to work with me
          or just say hi, feel free to reach out.
        </p>
        <a href="mailto:femisteves11@outlook.com"
          class="bg-white flex items-center justify-center p-1 rounded w-fit cursor-pointer"
        >
          <Icon name="ic:baseline-email" style="color: black" size="1rem" /> <span class="ml-1">Send
            me an email.</span>
        </a>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
const presentYear = computed(() => new Date().getFullYear());
</script>

<style scoped></style>
