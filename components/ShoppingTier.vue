<template>
  <div class="shopping-tier">
    <div class="tier-title">
      <h3>{{ title }}</h3>
    </div>
    <img :src='imgSrc'>
    <h2 class="tier-price" v-if="subscribed">{{discountPrice}}</h2>
    <h2 class="tier-price" v-else>{{price}}</h2>
    <a href="https://www.metageek.com/" target="_blank" class="shopping-tier__buy-now-btn">Buy Now</a>
    <ul>
      <li v-for="benefit in this.benefits" :key="benefit">
        <span v-if="benefit.addedBenefit" class="added-benefit">{{ benefit.text }}</span>
        <span v-else>{{ benefit.text }}</span>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    props: ['subscribed', 'title', 'imgSrc', 'benefitsObj', 'price', 'discountPrice'],
    data() {
      return {
        benefits: this.benefitsObj
      }
    }
  }

</script>

<style>
  .shopping-tier {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    width: 90%;
    max-width: 420px;
    background-color: #FFA6F8;
    margin: 0 15px 50px;
    border-radius: 25px;
    padding: 0 0 25px;
    box-shadow: 7px 7px 15px #d9d7cf,
      -7px -7px 15px #ffffff;
    font-size: 16px;
  }

  .shopping-tier img {
    margin-bottom: 25px;
    
  }

  .shopping-tier .tier-price {
    font-size: 3em;
      margin-bottom: 5px;
  }

  .tier-title {
    background-color: #B362AC;
    width: 100%;
    border-top-left-radius: 25px;
    border-top-right-radius: 25px;
    margin-bottom: 35px;
      padding: 15px 0;
  }

  .tier-title h3 {
    color: #fff;
    font-size: 2.5em;
    line-height: 1;
      margin-bottom: .2em;
  }

  .shopping-tier img {
    max-width: 125px;
  }

  .shopping-tier ul {
    list-style-type: none;
    margin: 0 auto;
    padding: 0;
    text-align: left;
    width: 90%;
    box-sizing: border-box;
  }

  .shopping-tier ul li {
    font-size: 1.1em;
      line-height: 2em;
    margin: 0;
    padding: 0;
  }

  .added-benefit {
    font-weight: 600;
  }

  .shopping-tier .shopping-tier__buy-now-btn{
    display: block;
    padding: .5em .75em;
    border-radius: 2em;
    margin: 15px 0;
    box-shadow: none;
    transition: .2s ease-out;
    color: inherit;
    border: 1px solid #6BB3AB;
    background-color: #70CCC2;
    font-size: 1.65em;
    text-transform: uppercase;
    color: #fff;
    font-weight: 600;
    text-decoration: none;
    transition: .2s ease-out;
  }
  
  .shopping-tier .shopping-tier__buy-now-btn:hover{
    background-color: #6BB3AB;
    transition: .2s ease-in;
  }

  @media screen and (min-width: 900px) {
    .shopping-tier {
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      align-items: center;
      margin: 0 15px 50px;
      border-radius: 25px;
      padding: 0 0 25px;
    }

    .shopping-tier img {
      margin-bottom: 25px;
    }

    .shopping-tier h2 {
      font-size: 2.5em;
    }

    .tier-title {
      border-top-left-radius: 25px;
      border-top-right-radius: 25px;
      margin-bottom: 35px;
      padding: 10px 0;

    }

    .tier-title h3 {
      font-size: 2em;
      margin-bottom: .2em;
    }

    .shopping-tier ul li {
      font-size: 1em;
      line-height: 1.75em;
    }
  }

  @media screen and (min-width: 1200px) {

    .shopping-tier h2 {
      font-size: 3em;
      margin-bottom: 25px;
    }

    .tier-title {
      margin-bottom: 35px;
      padding: 15px 0;

    }

    .tier-title h3 {
      font-size: 2.5em;
      margin-bottom: .2em;
    }

    .shopping-tier ul li {
      font-size: 1.25em;
      line-height: 2em;
    }

  }

</style>
