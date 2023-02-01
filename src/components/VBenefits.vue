<template>
  <div class="benefit">
    <div class="menu">
      <span class="material-icons"> <slot name="icon"></slot> </span>
    </div>
    <div class="content">
      <h1 class="title">
        <slot name="title"></slot>
      </h1>
      <h2 class="subtitle">
        <slot name="subtitle"></slot>
      </h2>
    </div>
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
  flex-basis: 45%;
  flex-wrap: wrap;
  flex-grow: 1;
  justify-content: center;
  align-items: center;
  gap: 10px;
  font-family: "Inter";
  font-style: normal;
  color: #1d1d1f;

  > .menu {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 70px;
    height: 70px;
    background: #f3fcf7;
    border-radius: 10px;

    > .material-icons {
      color: map-get($colors, "primary");
      font-size: 35px;
    }
  }

  > .content {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 10px;

    > .title {
      margin-top: 15px;
      font-size: 16px;
      font-weight: 400;
      line-height: 22px;
    }

    > .subtitle {
      font-weight: 500;
      font-size: 12px;
      line-height: 17px;
      opacity: 0.75;
    }
  }
}
@media screen and (min-width: 768px) {
  .benefit {
    flex-direction: row;
    flex-wrap: nowrap;
  }
}
</style>
