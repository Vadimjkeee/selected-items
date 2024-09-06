<template>
  <div class="items__list">
    <div v-for="item in filteredItems" :key="item.id" class="items__list--selected">
      {{ item.name }}
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      items: Array,
    },
    computed: {
      filteredItems() {
        return this.items.filter((item) => item !== null && item !== undefined);
    },
  },
};
</script>

<style scoped lang="scss">
.items__list {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;

  &--selected {
    padding: 0.5rem;
    background-color: green;
    border: 0.1rem solid #000;
  }
}
</style>
