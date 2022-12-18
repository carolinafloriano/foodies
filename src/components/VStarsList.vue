<template>
  <ul class="stars-list">
    <li class="item" v-for="(item, index) in items" :key="'item' + index">
      <span class="number"> {{ item.number }} </span>
      <span class="name"> {{ item.name }} </span>
    </li>
  </ul>
</template>

<script>
export default {
  name: "VStarsList",

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

.stars-list {
  display: flex;
  flex-direction: column;
  align-items: center;
  row-gap: 35px;
  margin-left: 20px;
  margin-top: 20px;
  font-size: 16px;

  .item {
    display: flex;
    flex-direction: column;
    align-items: center;
    row-gap: 10px;
    vertical-align: middle;
    justify-content: center;

    > .number {
      font-weight: 600;
      font-size: 40px;
      line-height: 48px;
      color: map-get($colors, "primary");
    }

    > .name {
      font-weight: 400;
      font-size: 15px;
      line-height: 18px;

      color: #1d1d1f;

      opacity: 0.65;
    }
  }
}
</style>
