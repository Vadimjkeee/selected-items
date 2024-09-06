<template>
  <div class="app">
    <div class="block block--top">
      <div class="block__choice">
        <SelectedList :items="selectedUserItems" />
      </div>
      <div class="block__choice">
        <SelectedList :items="[selectedChoiceItem]" />
      </div>
    </div>
    <div class="block block--bottom">
      <div class="block__choice">
        <SelectedItem :items="userItems" @selectItem="selectUserItem" />
      </div>
      <div class="block__choice">
        <SelectedItem :items="choiceItems" @selectItem="selectChoiceItem" single />
      </div>
    </div>
  </div>
</template>

<script>
import SelectedItem from './components/SelectedItem.vue';
import SelectedList from './components/SelectedList.vue';

export default {
  components: {
    SelectedItem,
    SelectedList,
  },
  data() {
    return {
      userItems: [
        { id: 1, name: 'leftItem1' },
        { id: 2, name: 'leftItem2' },
        { id: 3, name: 'leftItem3' },
        { id: 4, name: 'leftItem4' },
        { id: 5, name: 'leftItem5' },
        { id: 6, name: 'leftItem6' },
        { id: 7, name: 'leftItem7' },
        { id: 8, name: 'leftItem8' },
      ],
      choiceItems: [
        { id: 11, name: 'rightItem1' },
        { id: 12, name: 'rightItem2' },
        { id: 13, name: 'rightItem3' },
        { id: 14, name: 'rightItem4' },
        { id: 15, name: 'rightItem5' },
        { id: 16, name: 'rightItem6' },
        { id: 17, name: 'rightItem7' },
        { id: 18, name: 'rightItem8' },
      ],
      selectedUserItems: [],
      selectedChoiceItem: null,
    };
  },
  methods: {
    selectUserItem(item) {
      if (this.selectedUserItems.length < 6 && !this.selectedUserItems.includes(item)) {
        this.selectedUserItems.push(item);
      }
    },
    selectChoiceItem(item) {
      this.selectedChoiceItem = item;
    },
  },
};
</script>

<style scoped lang="scss">
.block{ 
  &--top, &--bottom {
    display: flex;
    justify-content: space-between;
    margin-bottom: 1.5rem;
  }

  &__choise {
      width: 48%;
  }
}
</style>
