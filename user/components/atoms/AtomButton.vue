<template>
  <button
    class="flex items-center justify-center focus:outline-none px-3 py-2 rounded text-button bg-white border-2 border-green-900 text-green-900"
    :disabled="$props.disabled"
    @click="$emit('click')"
  >
    <slot />
  </button>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  props: {
    color: { type: String, required: false, default: 'black' },
    outlined: { type: Boolean, required: false, default: false },
    disabled: { type: Boolean, required: false, default: false },
  },
});
</script>
