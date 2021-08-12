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

      <div v-if="items.length === 0">
        <h1>Kayıt Bulunamadı</h1>
      </div>
    </div>
    {{ searchQuery }}
  </div>
</template>

<style lang="scss" scoped>
.v-cards {
  @apply w-full md:w-9/12 bg-white rounded-lg p-6;

  &__container {
    @apply flex flex-wrap rounded-lg bg-gray-100 p-6 shadow-xl;

    height: 100%;
    max-height: 432px;
    overflow-y: scroll;
  }
}
</style>
