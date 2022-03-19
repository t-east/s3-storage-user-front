<template>
  <p class="text-sm">
    <slot />
    <span v-if="$props.required" class="font-normal text-xs text-red-500">必須</span>
  </p>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  props: {
    required: { required: false, type: Boolean, default: false },
  },
});
</script>
