<template>
  <input
    ref="input"
    class="border-2 border-green-900 bg-palpul-box-gray rounded py-2 px-2 focus:outline-none focus:ring-2 focus:ring-palpul-light-blue disabled:bg-gray-100 disabled:cursor-not-allowed"
    :value="value"
    :disabled="$props.disabled"
    :placeholder="$props.placeholder"
    :type="type"
    :min="$props.min"
    @input="$emit('input', $event.target.value)"
    @change="$emit('change', $event.target.value)"
    @blur="$emit('blur', $event.target.value)"
    @keyup.enter="$emit('onEnter', $event.target.value)"
  >
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  model: {
    prop: 'value',
    event: 'input',
  },
  props: {
    disabled: { type: Boolean, required: false, default: false },
    value: { type: [String, Date, Number], required: false, default: '' },
    placeholder: { type: String, required: false, default: '' },
    type: { type: String, required: false, default: '' },
    min: { type: String, required: false, default: '' },
  },
  methods: {
    focus(): void {
      const input: any = this.$refs.input;
      input.focus();
    },
  },
});
</script>

<style>
</style>
