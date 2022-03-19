<template>
  <div>
    <AtomFileInput
      v-if="!$props.value.exist"
      type="file"
      @change="selectFile"
      />
      <div v-else class="flex justify-center">
        <div>
          <img :src="$props.value.image" class="w-5/6 h-5/6">
          <p>{{ $props.value.name }}</p>
        </div>
      </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

import AtomFileInput from '~/components/atoms/AtomFileInput.vue'

import { SelectFile } from '~/interfaces/content';

export default Vue.extend({
  components: {
    AtomFileInput
  },
  props: {
    value: { type: Object as Vue.PropType<SelectFile>, required: false, default: {} }
  },
  methods: {
    selectFile(f:any):void {
      let file = new FormData();
      const selectedFile = {} as SelectFile
      if (f.type.startsWith("image/")) {
        selectedFile.image = window.URL.createObjectURL(f);
        selectedFile.name = f.name;
        selectedFile.type = f.type;
        selectedFile.exist = true
        file.append('content', f)
        file.append('name', f.name)
        selectedFile.file = file;
        this.$emit('input', selectedFile)
      }
    }
  }
});
</script>
