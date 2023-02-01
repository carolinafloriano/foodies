<template>
  <section
    class="vue-section"
    :class="{
      '-before': imageBefore,
      '-after': imageAfter,
      '-backgroundImage': showImageBackground,
      '-desktopView': desktopView,
    }"
  >
    <div class="call-to-action" v-if="showCallToAction">
      <h2 class="subtitle">
        <slot name="subtitle"></slot>
      </h2>
      <h1 class="title" :class="{ '-large': titleLarge }">
        <slot name="title"></slot>
      </h1>
      <p class="description" v-if="showDescription">
        <slot name="description"></slot>
      </p>
      <div class="action" v-if="showAction">
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
    showDescription: {
      type: Boolean,
      required: false,
    },
    showAction: {
      type: Boolean,
      required: false,
    },
    showDivisor: {
      type: Boolean,
      required: false,
    },
    desktopView: {
      type: Boolean,
      required: false,
    },
    imageBefore: {
      type: Boolean,
      required: false,
    },
    imageAfter: {
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
    showImageBackground: {
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
  gap: 15px;
  justify-content: center;
  text-align: center;
  align-items: center;
  padding: 25px;

  &.-before {
    > .image {
      order: 10;
    }
    > .call-to-action {
      order: 20;
    }
    > .content {
      order: 30;
    }
    > .divisor {
      order: 40;
    }
  }

  &.-backgroundImage {
    background: url("@/assets/images/others/rectangle.png") center no-repeat;
    background-size: cover;
    padding: 100px 60px;

    > .call-to-action {
      > .title {
        color: #f0f1ec;
      }
    }
  }

  .call-to-action {
    display: flex;
    flex-direction: column;
    row-gap: 20px;
    justify-content: center;
    text-align: center;
    align-items: center;
    order: 1;
    margin-top: 15px;
    color: #1d1d1f;

    > .subtitle {
      font-size: 15px;
      font-weight: 500;
      line-height: 18px;
    }

    > .title {
      font-weight: 500;
      font-size: 35px;
      line-height: 42px;

      &.-large {
        font-weight: 600;
        font-size: 51px;
        line-height: 62px;
      }
    }

    > .description {
      width: 100%;
      font-weight: 400;
      font-size: 14px;
      line-height: 159.4%;
    }

    > .action {
      width: 100%;
      margin-top: 30px;
    }
  }

  > .image {
    margin-top: 30px;
    order: 10;

    img {
      width: 100%;
    }

    &.-small {
      width: 100%;
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
      width: 100%;
    }
  }

  > .content {
    &.-flex {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      column-gap: 15px;
      row-gap: 40px;
      order: 20;
    }

    &.-chart {
      row-gap: 0;
    }

    &.-smallImage {
      width: 40%;
    }
  }

  > .divisor {
    width: 100%;
    margin-top: 35px;
    order: 30;
  }
}

@media screen and (min-width: 768px) {
  .vue-section {
    &.-desktopView {
      display: grid;
      grid-template-columns: 60% 1fr;
      grid-template-rows: auto auto auto;
      gap: 50px;
      padding: 50px 150px;
      box-sizing: border-box;
    }

    > .call-to-action {
      align-items: flex-start;
      justify-content: left;
      text-align: left;

      > .action {
        flex: auto;
        width: 40%;
      }
    }

    &.-backgroundImage {
      background-size: auto;

      > .call-to-action {
        > .action {
          width: 30%;
        }
      }
    }

    .content {
      width: 100%;
      box-sizing: border-box;

      &.-flex {
        flex-direction: row;
        flex-wrap: initial;
        gap: 40px;
        justify-content: space-around;
      }

      &.-chart {
        flex-wrap: wrap;
        gap: 0;
        justify-content: center;
      }
    }

    &.-before {
      display: flex;
      flex-direction: row;
      align-items: center;
      text-align: left;
      gap: 100px;

      > .call-to-action {
        align-items: initial;

        > .description {
          > .stars-list {
            display: flex;
            flex-direction: row;
            gap: 80px;
            justify-content: baseline;
          }

          > .item-list {
            margin-left: 0;
          }
        }

        > .action {
          flex: auto;
        }
      }
    }

    &.-after {
      display: flex;
      flex-direction: row;
      align-items: center;
      text-align: left;
      gap: 100px;

      > .image {
        order: 40;
        box-sizing: border-box;

        &.-small {
          width: 450px;
        }
      }
      > .call-to-action {
        align-items: initial;
        order: 10;

        > .description {
          > .stars-list {
            display: flex;
            flex-direction: row;
            gap: 80px;
            justify-content: baseline;
          }
        }

        > .action {
          flex: auto;
        }
      }
      > .content {
        order: 20;
      }
      > .divisor {
        order: 30;
      }
    }
  }
}

/* Positioning */

/* Display & Box Model */

/* Color */

/* Text */

/* Other */
</style>
