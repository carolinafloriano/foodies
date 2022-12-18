<template>
  <ul class="item-list">
    <li class="item" v-for="(item, index) in items" :key="'item' + index">
      <span class="material-icons"> done </span> {{ item }}
    </li>
  </ul>
</template>

<script>
export default {
  name: "VItemList",

  props: {
    items: {
      type: Array,
      required: true,
    },
  },
};
</script>
<style lang="scss">
@import "@/assets/styles/variables.scss";

.item-list {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  row-gap: 10px;
  margin-left: 20px;
  font-size: 16px;

  .item {
    display: flex;
    flex-direction: row;
    column-gap: 10px;
    align-items: center;
    vertical-align: middle;
  }

  .material-icons {
    font-size: 28px;
    font-weight: 700;
    color: map-get($colors, "primary");
  }
}
</style>
