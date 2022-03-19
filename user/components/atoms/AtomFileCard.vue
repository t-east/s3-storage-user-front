<template>
  <div>
    <img :src="$props.value.image" :class="'w-${$props.width} h-${$props.height}'">
    <p>{{ $props.value.name }}</p>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

import { SelectFile } from '~/interfaces/content';

export default Vue.extend({
  props: {
    value: { type: Object as Vue.PropType<SelectFile>, required: false, default: '' },
    width: { type: String, required: false, default: 'auto' },
    height: { type: String, required: false, default: 'auto' },
  },
});
</script>
