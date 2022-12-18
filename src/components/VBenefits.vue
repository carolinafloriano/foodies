<template>
  <div class="benefit">
    <div class="menu">
      <span class="material-icons"> <slot name="icon"></slot> </span>
    </div>
    <h1 class="title">
      <slot name="title"></slot>
    </h1>
    <h2 class="subtitle">
      <slot name="subtitle"></slot>
    </h2>
  </div>
</template>
<script>
export default {
  name: "VBenefits",
};
</script>
<style lang="scss">
@import "@/assets/styles/variables.scss";

.benefit {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  row-gap: 5px;
  font-family: "Inter";
  font-style: normal;
  color: #1d1d1f;

  .title {
    margin-top: 15px;
    font-size: 18px;
    font-weight: 400;
    line-height: 22px;
  }

  .subtitle {
    font-weight: 500;
    font-size: 14px;
    line-height: 17px;
    opacity: 0.75;
  }

  .menu {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 70px;
    height: 70px;
    background: #f3fcf7;
    border-radius: 10px;
  }

  .material-icons {
    color: map-get($colors, "primary");
    font-size: 35px;
  }
}
</style>
