<template>  
  <div class="items-block">
    <div
      v-for="item in items"
      :key="item.id"
      @click="selectItem(item)"
      class="item"
    >
      {{ item.name }}
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      items: Array,
    },
    methods: {
      selectItem(item) {
        this.$emit("selectItem", item);
      },
    },
  };
</script>

<style scoped lang="scss">
.items-block {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}

.item {
  padding: 0.5rem;
  background-color: gray;
  cursor: pointer;
  border: 0.1rem solid #000;
}
</style>
