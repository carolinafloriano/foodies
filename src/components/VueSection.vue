<template>
  <section class="vue-section" :class="{ '-before': imageBefore }">
    <div class="call-to-action" v-if="showCallToAction">
      <h2 class="subtitle">
        <slot name="subtitle"></slot>
      </h2>
      <h1 class="title" :class="{ '-large': titleLarge }">
        <slot name="title"></slot>
      </h1>
      <p class="description">
        <slot name="description"></slot>
      </p>
      <div class="action">
        <slot name="action"></slot>
      </div>
    </div>
    <div
      class="image"
      :class="{
        '-small': smallImage,
        '-medium': mediumImage,
        '-large': largeImage,
      }"
      v-if="showImage"
    >
      <slot name="image"></slot>
    </div>
    <div
      class="content"
      v-if="showContent"
      :class="{
        '-flex': contentFlex,
        '-chart': contentChart,
        '-smallImage': contentImage,
      }"
    >
      <slot name="content"></slot>
    </div>
    <div class="divisor" v-if="showDivisor">
      <hr />
    </div>
  </section>
</template>

<script>
export default {
  name: "VueSection",

  props: {
    showCallToAction: {
      type: Boolean,
      required: false,
    },
    showImage: {
      type: Boolean,
      required: false,
    },
    showContent: {
      type: Boolean,
      required: false,
    },
    showDivisor: {
      type: Boolean,
      required: false,
    },
    imageBefore: {
      type: Boolean,
      required: false,
    },
    titleLarge: {
      type: Boolean,
      required: false,
    },
    smallImage: {
      type: Boolean,
      required: false,
    },
    mediumImage: {
      type: Boolean,
      required: false,
    },
    largeImage: {
      type: Boolean,
      required: false,
    },
    contentFlex: {
      type: Boolean,
      required: false,
    },
    contentChart: {
      type: Boolean,
      required: false,
    },
    contentImage: {
      type: Boolean,
      required: false,
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/variables.scss";

.vue-section {
  display: flex;
  flex-direction: column;
  row-gap: 15px;
  align-items: center;
  justify-content: center;
  text-align: center;
  margin-top: 30px;

  &.-before {
    .image {
      order: 10;
    }
    .call-to-action {
      order: 20;
    }
    .content {
      order: 30;
    }
    .divisor {
      order: 40;
    }
  }

  .call-to-action {
    display: flex;
    flex-direction: column;
    row-gap: 20px;
    align-items: center;
    justify-content: center;
    text-align: center;
    order: 1;
    margin-top: 15px;
    width: 90%;
    color: #1d1d1f;
  }

  .subtitle {
    font-size: 15px;
    font-weight: 500;
    line-height: 18px;
  }

  .title {
    font-weight: 500;
    font-size: 35px;
    line-height: 42px;
    text-align: center;

    &.-large {
      font-weight: 600;
      font-size: 51px;
      line-height: 62px;
    }
  }

  .description {
    width: 100%;
    font-weight: 400;
    font-size: 14px;
    line-height: 159.4%;
  }

  .image {
    margin-top: 30px;
    order: 10;

    img {
      width: 100%;
    }

    &.-small {
      width: 90%;
      background: #f0f1ec;

      img {
        width: 88%;
        transform: translateY(-20px);
      }
    }
    &.-medium {
      width: 88%;
    }
    &.-large {
      width: 93%;
    }
  }

  .content {
    &.-flex {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      row-gap: 30px;
      justify-content: space-around;
      margin-top: 20px;
      order: 20;
    }

    &.-chart {
    }

    &.-smallImage {
      width: 40%;
    }
  }

  .action {
    width: 100%;
    margin-top: 30px;
  }

  .divisor {
    width: 100%;
    margin-top: 35px;
    order: 30;
  }
}

/* Positioning */

/* Display & Box Model */

/* Color */

/* Text */

/* Other */
</style>
