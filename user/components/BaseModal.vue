<template>
  <div
    class="fixed inset-0 h-screen flex items-center justify-center z-50"
    :class="$props.bgColor"
  >
    <div class="sm:w-80 w-5/6 max-w-lg modal-height bg-white text-black rounded-2xl px-8 my-12 relative">
      <slot />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  props: {
    bgColor: { type: String, default: 'bg-green-900' },
  },
});
</script>

<style scoped>
.modal-height {
  height: 85%
}
</style>