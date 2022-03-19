<template>
  <label class="border-2 border-green-900 rounded p-2">
    ファイルを選択
    <input
      ref="file"
      class="hidden"
      :disabled="$props.disabled"
      type="file"
      @change="selectFile"
    >
  </label>
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
  },
  methods: {
    selectFile(e:any):void {
      const files = this.$refs.file;
      const fileImg = files.files[0];
      this.$emit('change', fileImg)
    }
  }
});
</script>

<style>
</style>
