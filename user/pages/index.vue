<template>
  <div class="container">
    <RegisterModal v-if="isRegisterModal"/>
    <UploadModal/>
    <AtomFileCard />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

import RegisterModal from '~/components/organisms/RegisterModal.vue';
import UploadModal from '~/components/organisms/UploadModal.vue';
import AtomFileCard from '~/components/atoms/AtomFileCard.vue';

export default Vue.extend({
  components: {
    RegisterModal,
    AtomFileCard,
    UploadModal
  },
  data() {
    return {
      isRegisterModal: false
    }
  }
})
</script>
