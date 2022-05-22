<template>
  <button
    type="button"
    class="bg-blue-300 rounded-full hover:bg-black hover:text-white transition-colors duration-500"
    :class="smaller ? ['px-4', 'text-xs', 'py-1', 'uppercase'] : ['px-5', 'py-1.5', 'first-letter:uppercase']"
  >
    <slot />
  </button>
</template>

<script setup>
const props = defineProps({
  smaller: {
    type: Boolean,
    default: false,
  },
});
</script>