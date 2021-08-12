<script>
export default {
  name: 'VSearchInput',
  data() {
    return {
      searchingText: '',
    };
  },
  methods: {
    logSearchingText() {
      this.$emit('changeSearchingText', this.searchingText);
    },
  },
};
</script>

<template>
  <div class="search">
    <div class="search__container">
      <div class="search__icon-wrapper">
        <i class="search__icon fa fa-search"></i>
      </div>

      <input
        v-model="searchingText"
        type="text"
        class="search__input"
        placeholder="Search anything..."
        @keyup.enter="logSearchingText"
        @input="logSearchingText"
      >

      <div class="search__button-wrapper">
        <button
          class="search__button"
          @click="logSearchingText"
        >
          Search
        </button>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.search {
  @apply w-full md:w-9/12;

  &__container {
    @apply relative mb-4;
  }

  &__icon-wrapper {
    @apply absolute top-4 left-3;
  }

  &__icon {
    @apply text-gray-400 z-20 hover:text-gray-500;
  }

  &__input {
    @apply h-14 w-full pl-10 pr-20 rounded-lg z-0 focus:shadow focus:outline-none;
  }

  &__button-wrapper {
    @apply absolute top-2 right-2;
  }

  &__button {
    @apply h-10 w-20 text-white rounded-lg bg-red-500 hover:bg-red-600;
  }
}
</style>
