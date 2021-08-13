<script>
export default {
  name: 'VCard',
  props: {
    item: {
      type: Object,
    },
  },
};
</script>

<template>
  <div class="v-card">
    <div class="v-card__container">
      <div class="v-card__picture">
        <img
          class="w-full h-full object-cover"
          :src="item.picture"
          :alt="item.name"
        >
      </div>

      <div class="v-card__content">
        <h4 class="v-card__name">{{ item.name }}</h4>

        <h5 class="v-card__company">{{ item.company }}</h5>

        <h6 class="v-card__balance">{{ item.balance }}</h6>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.v-card {
  @apply w-full md:w-1/2 p-3;

  &__container {
    @apply p-3 flex bg-white rounded-lg;
  }

  &__picture {
    @apply h-36 w-36 rounded overflow-hidden flex-shrink;

    flex-basis: 40%;
  }

  &__content {
    @apply px-6 py-3;

    flex-basis: 60%;
  }

  &__name {
    @apply text-xl font-semibold text-gray-700;
  }

  &__company {
    @apply text-base text-gray-600;
  }

  &__balance {
    @apply text-sm text-gray-400;
  }
}
</style>
