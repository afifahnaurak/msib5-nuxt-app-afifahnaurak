<template>
  <div
    class="mt-7 max-w-sm mx-auto text-center p-3 rounded-md bg-white shadow-md h-full"
  >
    <p class="mt-7 text-7xl font-bold">{{ error.statusCode }}</p>
    <p class="mt-7 text-6xl">Ooops.</p>
    <p class="mt-7">{{ error.message }}</p>
    <button
      class="bg-blue-900 px-2 py-1 rounded-md hover:bg-blue-950 mb-4 text-white my-7"
      @click="handleClearError"
    >
      Go Home...
    </button>
  </div>
</template>

<script setup>
defineProps(["error"]);

const handleClearError = () => clearError({ redirect: "/" });
</script>

<style scoped></style>
