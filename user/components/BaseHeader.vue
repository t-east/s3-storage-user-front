<template>
  <header class="h-14 py-2 px-4 flex justify-between items-center text-white">
    <div @click="home()">
      aaa
    </div>
    <slot name="right" />
  </header>
</template>
<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  components: {
  },
  methods: {
    home(): void {
    //   // @ts-ignore
    //   if (this.$store.$auth.loggedIn && this.$auth.user.user_type === 'consumer') {
    //     this.$router.push({ path: '/home' });
    //     // @ts-ignore
    //   } else if (this.$store.$auth.loggedIn && this.$auth.user.user_type === 'stylist') {
    //     this.$router.push({ path: '/s/home' });
    //   } else {
    //     this.$router.push({ path: '/' });
    //   }
    },
  },
});
</script>