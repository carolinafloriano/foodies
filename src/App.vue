<template>
  <div id="app">
    <VHeader></VHeader>
    <div class="container">
      <VueSection
        show-call-to-action
        show-image
        show-content
        show-divisor
        title-large
        large-image
        content-flex
        small-image
      >
        <template #title>We're Serious For Food</template>
        <template #description
          >We strive to provide a space where guests can connect with themselves
          and explore their full potential, offering a safe place.</template
        >
        <template #action>
          <VButton primary large> Get Started </VButton></template
        >
        <template #image><img :src="imgWoman" /></template>
        <template #content>
          <img :src="imgLogo01" />
          <img :src="imgLogo02" />
          <img :src="imgLogo03" />
        </template>
      </VueSection>
      <VueSection show-content show-divisor content-flex>
        <template #content>
          <VBenefits>
            <template #icon>local_shipping</template>
            <template #title>Free Shipping</template>
            <template #subtitle>Orders over $140</template>
          </VBenefits>
          <VBenefits>
            <template #icon>wallet</template>
            <template #title>Quick Payment</template>
            <template #subtitle>100% secure payment</template>
          </VBenefits>
          <VBenefits>
            <template #icon>attach_money</template>
            <template #title>Special Promo</template>
            <template #subtitle>Get special promo</template>
          </VBenefits>
          <VBenefits>
            <template #icon>support_agent</template>
            <template #title>24/7 Support</template>
            <template #subtitle>Ready Support</template>
          </VBenefits>
        </template>
      </VueSection>
      <VueSection show-call-to-action show-image image-before small-image>
        <template #subtitle>Our Benefit</template>
        <template #title>The More Healthy Food The Better</template>
        <template #description>
          <VItemList :items="itens01"></VItemList>
        </template>
        <template #image><img :src="imgFoodies01" /></template>
      </VueSection>
      <VueSection show-call-to-action show-image image-before small-image>
        <template #subtitle>Ours Stars</template>
        <template #title>Veggie Food Goes On And Always On</template>
        <template #description
          ><VItemStars :items="stars"></VItemStars>
        </template>
        <template #image><img :src="imgFoodies02" /></template>
        <template #action>
          <VButton primary large> Get Special Promo </VButton></template
        >
      </VueSection>
      <VueSection show-call-to-action show-content content-flex>
        <template #subtitle>Ours Features</template>
        <template #title>Variety Of Veggie Foods</template>
        <template #content>
          <VFeature :photo="imgFoodies03">
            <template #headline>Veggies Are Forever</template>
            <template #details>We offer the following services</template>
          </VFeature>
          <VFeature :photo="imgFoodies03">
            <template #headline>Veggies Are Forever</template>
            <template #details>We offer the following services</template>
          </VFeature>
        </template>
      </VueSection>
    </div>
  </div>
</template>

<script>
import VHeader from "@/components/VHeader";
import VButton from "@/components/VButton.vue";
import VueSection from "@/components/VueSection.vue";
import VBenefits from "@/components/VBenefits.vue";
import VItemList from "@/components/VItemList.vue";
import VItemStars from "@/components/VStarsList.vue";
import VFeature from "@/components/VFeature.vue";

import woman from "@/assets/images/others/woman.png";
import logo1 from "@/assets/images/logos/logo-01.png";
import logo2 from "@/assets/images/logos/logo-02.png";
import logo3 from "@/assets/images/logos/logo-03.png";
import foodies_01 from "@/assets/images/foodies/foodies_01.png";
import foodies_02 from "@/assets/images/foodies/foodies_02.png";
import foodies_03 from "@/assets/images/foodies/foodies_03.png";

export default {
  name: "App",
  components: {
    VHeader,
    VButton,
    VueSection,
    VBenefits,
    VItemList,
    VItemStars,
    VFeature,
  },

  data() {
    return {
      imgWoman: woman,
      imgLogo01: logo1,
      imgLogo02: logo2,
      imgLogo03: logo3,
      imgFoodies01: foodies_01,
      imgFoodies02: foodies_02,
      imgFoodies03: foodies_03,

      itens01: [
        "Be Alive With Healthy Food",
        "It's The Place To Be",
        "Nonstop Veggie Food",
        "The Best Silk Dish in Town",
        "Truffles, Egg & Pumpkin Spice",
      ],
      stars: [
        { number: "1,500", name: "Sold Product" },
        { number: "500", name: "Positive Feedback" },
        { number: "400", name: "Official Store" },
      ],
    };
  },
};
</script>

<style lang="scss">
@import url("@/assets/styles/all.scss");

#app {
  font-family: "Inter", Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: calc(100vh * 5);
  display: flex;
  flex-direction: column;

  align-items: center;
}

.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 95%;
}
</style>
