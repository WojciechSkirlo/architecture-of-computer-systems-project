<template>
  <label class="w-full">
    <input
      type="text"
      :value="modelValue"
      :disabled="inputDisabled"
      maxlength="2"
      @input="$emit('update:modelValue', $event.target.value)"
      class="w-full px-4 py-1 border outline-none appearance-none"
      :class="inputDisabled ? ['bg-gray-300', 'border-gray-300', 'text-gray-700'] : ['focus:border-blue-300', 'border-black']"
      v-bind="!inputDisabled && { placeholder: '00' }"
    />
  </label>
</template>
<script setup>
defineProps({
  modelValue: {
    type: String,
    default: "",
  },

  inputDisabled: {
    type: Boolean,
    default: false,
  },
});

defineEmits(["update:modelValue"]);
</script>