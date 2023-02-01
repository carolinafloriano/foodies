<template>
  <div class="product-view" :class="{ '-contrast': contrastProduct }">
    <img class="fruit" :src="image" />
    <div class="avaliation">
      <span class="material-icons star" v-for="n in 5" :key="n"> star </span>
    </div>
    <h1 class="name">
      {{ name }}
    </h1>
    <div class="prices">
      <span class="original">${{ value }}</span>
      <span class="promotion">${{ promotion }}</span>
    </div>
    <VButton tertiary large>Buy Now</VButton>
  </div>
</template>

<script>
import VButton from "@/components/VButton.vue";

export default {
  name: "VProduct",
  components: {
    VButton,
  },
  props: {
    image: {
      type: String,
      required: true,
    },
    value: {
      type: String,
      required: true,
    },
    promotion: {
      type: String,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    contrastProduct: {
      type: Boolean,
      required: false,
    },
  },
};
</script>
<style lang="scss">
@import "@/assets/styles/variables.scss";

.product-view {
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 25px;
  justify-content: center;
  align-items: center;
  border: 2px solid #d6d6d6;
  padding: 25px;

  &.-contrast {
    border: 2px solid map-get($colors, "primary");
  }

  > .fruit {
    width: 70%;
  }

  > .avaliation {
    margin-top: -20px;

    > .star {
      color: map-get($colors, "primary");
    }
  }

  > .name {
    font-weight: 400;
    font-size: 20px;
    line-height: 24px;
    color: #1d1d1f;
  }

  > .prices {
    display: flex;
    flex-direction: row;
    column-gap: 10px;

    > .original {
      font-weight: 600;
      font-size: 20px;
      line-height: 24px;
      text-decoration-line: line-through;
      color: #767675;
      opacity: 0.35;
    }

    > .promotion {
      font-weight: 400;
      font-size: 20px;
      line-height: 24px;
      color: map-get($colors, "primary");
    }
  }
}

@media screen and (min-width: 768px) {
  .product-view {
    padding: 35px;
  }
}
</style>
