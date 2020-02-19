<template>
  <div class="tiered-shopping">
    <div class="recurring-option">
      <h3>Save 14% With a Yearly Subscription!</h3>
      <SubscriptionSwitch :recurring.sync="recurring" />
      <h4 v-if="recurring">Yearly Subscription</h4>
      <h4 v-else>One-time Purchase</h4>
    </div>
    <div class="tiered-shopping__container">
      <ShoppingTier title="Starter Box" :subscribed="recurring"
        img-src="https://s3-us-west-2.amazonaws.com/huesalonboise.com/ValentineGeek-hearts--white.svg"
        :benefits-obj="tier1" price="$15" discount-price="$12.90" />
      <ShoppingTier title="Classic Box" :subscribed="recurring"
        img-src="https://s3-us-west-2.amazonaws.com/huesalonboise.com/ValentineGeek-popular.svg"
        :benefits-obj="tier2" price="$25" discount-price="$21.50" />
      <ShoppingTier title="Premium Box" :subscribed="recurring"
        img-src="https://s3-us-west-2.amazonaws.com/huesalonboise.com/ValentineGeek-love-volcano.svg"
        :benefits-obj="tier3" price="$50" discount-price="$43.00" />
    </div>
  </div>
</template>

<script>
  import SubscriptionSwitch from '~/components/SubscriptionSwitch.vue'
  import ShoppingTier from '~/components/ShoppingTier.vue'
  export default {
    components: {
      SubscriptionSwitch,
      ShoppingTier
    },
    methods: {

    },
    data() {
      return {
        recurring: true,
        tier1: {
          "benefit1": {
            "text": "Simple cardboard box (6 in. x 3 in.)",
            "addedBenefit": false
          },
          "benefit2": {
            "text": "Set of 4 markers ",
            "addedBenefit": false
          },
          "benefit3": {
            "text": "2 Sheets of stickers",
            "addedBenefit": false
          },
          "benefit4": {
            "text": "25 Valentine’s Day cards (3 themes available) ",
            "addedBenefit": false
          }
        },
        tier2: {
          "benefit1": {
            "text": "Corrugated cardboard box (10 in. x 10 in.)",
            "addedBenefit": false
          },
          "benefit2": {
            "text": "Set of 10 deluxe markers",
            "addedBenefit": false
          },
          "benefit3": {
            "text": "4 Sheets of stickers",
            "addedBenefit": false
          },
          "benefit4": {
            "text": "25 Valentine’s Day cards (5 themes available)",
            "addedBenefit": false
          },
          "benefit5": {
            "text": "Set of 4 washable paints with brush",
            "addedBenefit": true
          },
          "benefit6": {
            "text": "6 Valentine cut-outs",
            "addedBenefit": true
          }
        },
        tier3: {
          "benefit1": {
            "text": " Corrugated cardboard box (choose from 10 in. x 10 in. OR 12 in. x 12 in.)",
            "addedBenefit": false
          },
          "benefit2": {
            "text": "Set of 10 deluxe markers",
            "addedBenefit": false
          },
          "benefit3": {
            "text": "6 Sheets of stickers",
            "addedBenefit": false
          },
          "benefit4": {
            "text": "25 Valentine’s Day cards (10 themes available)",
            "addedBenefit": false
          },
          "benefit5": {
            "text": "Set of 6 washable paints with brush",
            "addedBenefit": false
          },
          "benefit6": {
            "text": "10 Valentine cut-outs",
            "addedBenefit": false
          },
          "benefit7": {
            "text": "4 Design templates",
            "addedBenefit": true
          }
        }
      }
    }
  }

</script>

<style>
  .tiered-shopping {
    width: 100%;
    font-size: 16px;
    margin-bottom: 75px;
  }

  .tiered-shopping .recurring-option {
    margin-bottom: 35px;
  }

  .tiered-shopping .recurring-option h3 {
    font-size: 1.55em;
    margin-bottom: 24px;
  }

  .tiered-shopping .recurring-option h4 {
      font-size: 1.35em;
  }

  .tiered-shopping__container {
    display: flex;
    justify-content: center;
    align-items: center;
    align-items: flex-start;
    flex-direction: column;
  }

  .tiered-shopping__container>div{
      width: 90%;
      margin: 0 auto 50px;
  }
 @media screen and (min-width: 900px) {
     .tiered-shopping .recurring-option h3 {
    font-size: 3em;
    margin-bottom: 24px;
  }
     .tiered-shopping__container {
    display: flex;
    justify-content: center;
    align-items: center;
    align-items: flex-start;
    flex-direction: row;
  }
  .tiered-shopping__container>div{
      width: 30%;
      margin: 0 15px 50px;
  }
 }

</style>
