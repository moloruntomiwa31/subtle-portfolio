<template>
  <div
    class="flex justify-center items-center p-4 rounded-md bg-[#EFF3EA]"
  >
    {{ content }}
  </div>
</template>

<script setup lang="ts">
defineProps<{
  content: string;
}>();
</script>

<style scoped></style>
