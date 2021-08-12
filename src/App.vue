<script>
import { mapGetters } from 'vuex';

export default {
  name: 'App',
  computed: {
    ...mapGetters(['getCustomers']),
  },
};
</script>

<template>
  <div id="app">
    <div class="container mx-auto flex flex-col items-center mt-16">
    </div>
  </div>
</template>

<style lang="scss">
</style>
