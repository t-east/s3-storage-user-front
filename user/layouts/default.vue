<template>
  <div class="">
    <BaseHeader class="bg-green-900">
      <template #right>
        <div class="flex items-center space-x-2 cursor-pointer" @click="$emit('open-menu')">
          <span class="inline-block align-middle text-lg py-2">
            asd
          </span>
        </div>
      </template>
    </BaseHeader>
    <div class="">
      <Nuxt/>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

import BaseHeader from '~/components/BaseHeader.vue';

export default Vue.extend({
  components: {
    BaseHeader
  }
})
</script>
