<template>
  <div class="feature-item">
    <img class="photo" :src="photo" />
    <div class="information">
      <h1 class="headline">
        <slot name="headline"></slot>
      </h1>
      <p class="details">
        <slot name="details"></slot>
      </p>
      <VButton secondary large>Discover Now</VButton>
    </div>
  </div>
</template>

<script>
import VButton from "@/components/VButton.vue";

export default {
  name: "VFeature",
  components: {
    VButton,
  },
  props: {
    photo: {
      type: String,
      required: true,
    },
  },
};
</script>
<style lang="scss">
@import "@/assets/styles/variables.scss";

.feature-item {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  row-gap: 0;

  > .photo {
    width: 100%;
  }

  > .information {
    display: flex;
    flex-direction: column;
    padding: 35px 50px 35px 35px;
    row-gap: 30px;
    text-align: left;
    background-color: #f0f1ec;
    border: 2px solid map-get($colors, "primary");

    > .headline {
      font-weight: 500;
      font-size: 32px;
      line-height: 39px;
    }

    > .details {
      font-weight: 400;
      font-size: 16px;
      line-height: 19px;
    }
  }
}
</style>
