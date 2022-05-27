<template>
  <button
    type="button"
    class="transition-colors duration-500 bg-blue-300 rounded-full hover:bg-black hover:text-white"
    :class="!bigger ? ['px-4', 'text-xs', 'py-1', 'uppercase'] : ['px-5', 'py-1.5', 'first-letter:uppercase']"
  >
    <slot />
  </button>
</template>

<script setup>
const props = defineProps({
  bigger: {
    type: Boolean,
    default: false,
  },
});
</script>