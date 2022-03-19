<template>
  <div class="text-sm">
    <span>
      {{ $props.label }}
    </span>
    <span v-if="$props.required" class="ml-2 text-palpul-red">
      必須
    </span>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  props: {
    label: { required: true, type: String },
    required: { required: false, type: Boolean, default: false },
  },
});
</script>
