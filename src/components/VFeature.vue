<template>
  <div
    class="feature-item"
    :class="{
      '-invert': invert,
    }"
  >
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
    invert: {
      type: Boolean,
      required: false,
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
    border: 1px solid map-get($colors, "primary");
    box-sizing: border-box;

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
@media screen and (min-width: 768px) {
  .feature-item {
    flex-direction: row;

    > .photo {
      flex: 1;
      width: 310px;
      height: 310px;
    }

    > .information {
      flex: 1;
      width: 310px;
      height: 310px;
      padding: 50px 20px 50px 40px;
      box-sizing: border-box;
    }

    &.-invert {
      flex-direction: row-reverse;
    }
  }
}
</style>
