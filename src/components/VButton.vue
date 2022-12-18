<template>
  <button
    type="button"
    class="action-button"
    :class="{
      '-primary': primary,
      '-secondary': secondary,
      '-tertiary': tertiary,
      '-large': large,
    }"
  >
    <slot></slot>
    <span class="material-icons arrow"> arrow_right_alt </span>
  </button>
</template>

<script>
export default {
  name: "VButton",

  props: {
    primary: {
      type: Boolean,
      required: false,
    },
    secondary: {
      type: Boolean,
      required: false,
    },
    tertiary: {
      type: Boolean,
      required: false,
    },
    large: {
      type: Boolean,
      required: false,
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/reset.scss";
@import "@/assets/styles/variables.scss";
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.2.0/css/all.min.css");
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@900&display=swap");

.action-button {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  column-gap: 10px;
  border: 0;
  font-size: 16px;

  &.-primary {
    background-color: map-get($colors, "primary");
    color: #ffffff;
    width: 100%;
    height: 68px;
    font-weight: 400;
  }

  &.-secondary {
    background-color: #f0ede2;
    color: map-get($colors, "primary");
    font-weight: 500;
    line-height: 18.15px;
    width: 168px;
    height: 42px;
    padding: 10px;
  }

  &.-tertiary {
    width: 177px;
    height: 57px;
    background-color: #ffffff;
    color: map-get($colors, "primary");
    border: 2px solid map-get($colors, "primary");
    font-weight: 400;
  }

  &.-large {
    .material-icons {
      font-size: 2em;
    }
  }
}
</style>
