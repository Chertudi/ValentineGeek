<template>
  <section class="container">
    <Logo />
    <h1 class="title">ValentineGeek</h1>
    <h2>Valentines Day in a Box</h2>
    <img src="~/assets/ValentineGeek-hero.svg" class="valentine-hero"
      alt="ValentineGeek's Premium Valentines Day in a Box">
    <p>Working parents are busy and Valentine’s Day comes at an especially hectic time of year. Keeping up with the
      demands of your child's Valentine's Day Activities has never been more difficult.</p>

    <p>ValentineGeek helps make sure your child has a Valentine's Day worth remembering. With our yearly subscription
      option you will always be prepared for cupid's favorite holiday.</p>

    <h2>Check Out Our Valentine's Subscription Options</h2>

    <TieredShopping />

    <ValentinesFooter />



  </section>
</template>

<script>
  import Logo from '~/components/Logo.vue'
  import Benefit from '~/components/Benefit.vue'
  import ValentinesFooter from '~/components/ValentinesFooter.vue'
  import TieredShopping from '~/components/TieredShopping.vue'

  export default {
    components: {
      Logo,
      Benefit,
      TieredShopping,
      ValentinesFooter
    }
  }

</script>

<style>
  .container {
    margin: 0 auto;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    flex-direction: column;
    background-color: #fffdf3;
    padding-top: 15px;
  }

  .title {
    font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
      'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
    display: block;
    font-weight: 300;
    font-size: 3.5em;
    color: #35495e;
    letter-spacing: 1px;
  }

  .container h2 {
    font-size: 1.55em;
    margin-bottom: 75px;
  }

  .container .valentine-hero {
    max-width: 915px;
    width: 90%;
    margin-bottom: 75px;
  }

  .container>p {
    font-size: 1.15em;
    width: 85%;
    max-width: 800px;
    margin-bottom: 45px
  }


  .subtitle {
    font-weight: 300;
    font-size: 42px;
    color: #526488;
    word-spacing: 5px;
    padding-bottom: 15px;
  }

  .links {
    padding-top: 15px;
  }

  @media screen and (min-width: 800px) {
    .title {
      font-size: 100px;
      letter-spacing: 1px;
    }

    .container h2 {
      font-size: 2.75em;
      margin-bottom: 75px;
    }

    .container>p {
      font-size: 1.5em;
      margin-bottom: 45px
  }
  }

</style>
