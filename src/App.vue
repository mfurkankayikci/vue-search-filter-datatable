<script>
import { mapGetters } from 'vuex';
import VSearchInput from './components/VSearchInput.vue';
import VCards from './components/VCards.vue';

export default {
  name: 'App',
  components: {
    VSearchInput,
    VCards,
  },
  data() {
    return {
      searchQuery: '',
    };
  },
  computed: {
    ...mapGetters(['getCustomers']),

    customers() {
      return this.getCustomers
        .filter((item) => item.name.toLowerCase().includes(this.searchQuery.toLowerCase()));
    },
  },
  methods: {
    setSearchingText(value) {
      this.searchQuery = value;
    },
  },
};
</script>

<template>
  <div id="app">
    <div class="container mx-auto flex flex-col items-center mt-16">
      <v-search-input
        @changeSearchingText="setSearchingText"
      />

      <v-cards
        :searching-text="searchQuery"
        :items="customers"
      />
    </div>
  </div>
</template>

<style lang="scss">
#app {
  @apply w-screen h-screen bg-gray-100 flex items-center justify-center overflow-hidden
}
</style>
