<template>
  <div>
    <InputLabel class="py-2" :required="$props.required">
      {{ $props.label }}
    </InputLabel>
    <AtomInput
      :value="$props.value"
      :type="$props.type"
      class="w-full bg-palpul-box-gray h-full"
      :placeholder="$props.placeholder"
      @input="$emit('input', $event)"
    />
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

import AtomInput from '~/components/atoms/AtomInput.vue';
import InputLabel from '~/components/molecules/InputLabel.vue';

export default Vue.extend({
  components: {
    AtomInput,
    InputLabel,
  },
  props: {
    label: { type: String, required: true },
    value: { type: String, required: false, default: '' },
    type: { type: String, required: false, default: 'text' },
    placeholder: { type: String, required: false, default: '' },
    required: { type: Boolean, required: false, default: false },
  },
});

</script>
