<template>
  <div id="app">
    <VHeader></VHeader>
    <div class="container">
      <VueSection
        show-call-to-action
        show-image
        show-content
        show-description
        show-action
        show-divisor
        title-large
        large-image
        content-flex
        desktop-view
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
      <VueSection show-content show-divisor content-flex content-benefits>
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
      <VueSection
        show-call-to-action
        show-image
        show-description
        small-image
        position-image="-before"
      >
        <template #subtitle>Our Benefit</template>
        <template #title>The More Healthy Food The Better</template>
        <template #description>
          <VItemList :items="itens01"></VItemList>
        </template>
        <template #image><img :src="imgFoodies01" /></template>
      </VueSection>
      <VueSection
        show-call-to-action
        show-image
        show-description
        show-action
        small-image
        :position-image="position"
      >
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
      <VueSection
        show-call-to-action
        show-content
        content-flex
        content-chart
        elements-center
      >
        <template #subtitle>Ours Features</template>
        <template #title>Variety Of Veggie Foods</template>
        <template #content>
          <VFeature :photo="imgFoodies03">
            <template #headline>Veggies Are Forever</template>
            <template #details>We offer the following services</template>
          </VFeature>
          <VFeature :photo="imgFoodies04">
            <template #headline>Good For Your Skin</template>
            <template #details>We offer the following services</template>
          </VFeature>
          <VFeature :photo="imgFoodies05" invert>
            <template #headline>Veggie Food Grove</template>
            <template #details>We offer the following services</template>
          </VFeature>
          <VFeature :photo="imgFoodies06" invert>
            <template #headline>That Comes Close</template>
            <template #details>We offer the following services</template>
          </VFeature>
        </template>
      </VueSection>
      <VueSection show-call-to-action show-content content-flex elements-center>
        <template #subtitle>Our Product</template>
        <template #title>Most Popular Product</template>
        <template #content>
          <VProduct
            :image="imgBanana"
            value="29"
            promotion="25"
            name="Summer Veganie"
            contrast-product
          ></VProduct>
          <VProduct
            :image="imgPapaya"
            value="29"
            promotion="25"
            name="Greanie Seafood"
          ></VProduct>
          <VProduct
            :image="imgAvocado"
            value="29"
            promotion="25"
            name="Fresh Vegetable"
          ></VProduct>
          <VProduct
            :image="imgTangerine"
            value="29"
            promotion="25"
            name="Fresh Meatyus"
          ></VProduct>
        </template>
      </VueSection>
      <VueSection
        show-call-to-action
        show-action
        show-image-background
        elements-center
      >
        <template #title>Veggie Foods? Ingredients You Want To Try</template>
        <template #action>
          <VButton primary large> Get Started </VButton></template
        >
      </VueSection>
      <VFooter></VFooter>
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
import VProduct from "@/components/VProduct.vue";
import VFooter from "@/components/VFooter.vue";

import woman from "@/assets/images/others/woman.png";
import logo1 from "@/assets/images/logos/logo-01.png";
import logo2 from "@/assets/images/logos/logo-02.png";
import logo3 from "@/assets/images/logos/logo-03.png";
import foodies_01 from "@/assets/images/foodies/foodies_01.png";
import foodies_01_desktop from "@/assets/images/foodies/foodies_01_desktop.png";
import foodies_02 from "@/assets/images/foodies/foodies_02.png";
import foodies_02_desktop from "@/assets/images/foodies/foodies_02_desktop.png";
import foodies_03 from "@/assets/images/foodies/foodies_03.png";
import foodies_04 from "@/assets/images/foodies/foodies_04.png";
import foodies_05 from "@/assets/images/foodies/foodies_05.png";
import foodies_06 from "@/assets/images/foodies/foodies_06.png";
import fruit_banana from "@/assets/images/foodies/fruit_banana.png";
import fruit_papaya from "@/assets/images/foodies/fruit_papaya.png";
import fruit_avocado from "@/assets/images/foodies/fruit_avocado.png";
import fruit_tangerine from "@/assets/images/foodies/fruit_tangerine.png";

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
    VProduct,
    VFooter,
  },

  data() {
    return {
      imgWoman: woman,
      imgLogo01: logo1,
      imgLogo02: logo2,
      imgLogo03: logo3,
      imageFoodies01: foodies_01,
      imageFoodies01_desktop: foodies_01_desktop,
      imageFoodies02: foodies_02,
      imageFoodies02_desktop: foodies_02_desktop,
      imgFoodies03: foodies_03,
      imgFoodies04: foodies_04,
      imgFoodies05: foodies_05,
      imgFoodies06: foodies_06,
      imgBanana: fruit_banana,
      imgPapaya: fruit_papaya,
      imgAvocado: fruit_avocado,
      imgTangerine: fruit_tangerine,

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
      screenWidth: "",
    };
  },

  computed: {
    imgFoodies01() {
      console.log(this.screenWidth);
      if (this.screenWidth >= 768) {
        return this.imageFoodies01_desktop;
      } else {
        return this.imageFoodies01;
      }
    },
    imgFoodies02() {
      console.log(this.screenWidth);
      if (this.screenWidth >= 768) {
        return this.imageFoodies02_desktop;
      } else {
        return this.imageFoodies02;
      }
    },
    position() {
      console.log(this.screenWidth);
      if (this.screenWidth >= 768) {
        return "-after";
      } else {
        return "-before";
      }
    },
  },

  mounted() {
    this.screenWidth = screen.width;

    window.addEventListener("resize", () => {
      this.screenWidth = screen.width;
    });
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
  overflow: hidden;

  > .container {
    display: flex;
    flex-direction: column;
    row-gap: 20px;
    padding-right: 50px;
    padding-left: 50px;
  }
}

@media screen and (min-width: 768px) {
  #app {
    height: calc(100vh * 4);

    > .container {
      padding-right: 100px;
      padding-left: 100px;
      row-gap: 80px;
    }
  }
}
</style>
