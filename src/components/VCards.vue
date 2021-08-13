<script>
import VCard from './VCard.vue';

export default {
  name: 'VDataTable',
  components: {
    VCard,
  },
  props: {
    searchQuery: {
      type: String,
    },
    items: {
      type: Array,
    },
  },
};
</script>

<template>
  <div class="v-cards">
    <div class="v-cards__container">
      <v-card
        v-for="cardItem in items"
        :key="cardItem.index"
        :item="cardItem"
      />

      <template v-if="items.length === 0">
        <h1 class="text-xl text-gray-400">No Result Found</h1>
      </template>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.v-cards {
  @apply w-full md:w-9/12 bg-white rounded-lg p-2 md:p-6;

  &__container {
    @apply flex flex-wrap justify-center items-center rounded-lg bg-gray-100 p-2 md:p-6 shadow-xl;

    height: 432px;
    overflow-y: auto;
  }
}
</style>
