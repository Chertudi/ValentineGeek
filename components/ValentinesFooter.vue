<template>
  <footer>
    <div class="social-media">
      <ul>
        <li>
          <a href="http://www.facebook.com/pages/MetaGeek/322588047766226">
            <img src="~assets/logo-facebook.svg" alt="Facebook">
          </a>
        </li>
        <li>
          <a href="http://twitter.com/metageek">
            <img src="~assets/logo-twitter.svg" alt="Facebook">
          </a>
        </li>
        <li>
          <a href="https://www.pinterest.com/">
            <img src="~assets/logo-pinterest.svg" alt="Facebook">
          </a>
        </li>
      </ul>
    </div>
    <div class="logo-container">
      <Logo />
      <p class="copyright">&copy; {{ copyrightYear }} ValentineGeek, LLC. All Rights reserved.</p>
    </div>
    <div class="contact-us">
      <a href="mailto:matthew.chertudi@gmail.com">Email Us!</a>
      <a href="tel:+2089212556">Telephone: (208)921-2556</a>
    </div>
  </footer>
</template>

<script>
  import Logo from '~/components/Logo.vue'
  export default {
    components: {
      Logo
    },
    computed: {
      copyrightYear: function () {
        let d = new Date()

        return d.getFullYear();
      }
    }

  }

</script>

<style>
  footer {
    display: flex;
    justify-content: center;
    font-size: 16px;
    flex-direction: column;
    width: 100%;
    background-color: #FFA6F8;
    padding: 15px 0;
    color: #313131;
    box-sizing: border-box;
    max-width: 1920px;
    margin: 0 auto;
  }

  footer div.social-media {
    display: flex;
    justify-content: center;
    align-items: center;
    order: 1;
  }

 

  .social-media ul {
    list-style: none;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0;
    padding: 0;
  }

  .social-media ul li {
    border-radius: 50%;
    /* border: 1px solid black; */
    width: 40px;
    height: 40px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 5px;
    filter: opacity(.75);
    transition: .2s ease-out;
    box-shadow: none;
  }

  .social-media ul li:hover {
    transition: .2s ease-in;
    filter: opacity(.95);
    box-shadow: 5px 5px 10px #d98dd3,
      -5px -5px 7px #ffbfff;
    cursor: pointer;
  }

  .social-media ul li a {
    display: block;
    height: 20px;
    width: 20px;
  }

  .social-media img {
    width: 20px;
    height: 20px;
  }

   footer div.logo-container {
    padding-top: 25px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    min-height: 230px;
    order: 3;
  }

  .logo-container p.copyright {
    font-size: 1em;
  }

  footer div.contact-us {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    order: 2;
  }

  .contact-us a {
    display: block;
    padding: .5em .75em;
    border-radius: 2em;
    margin: 0px 0;
    box-shadow: none;
    transition: .2s ease-out;
    color: inherit;
    text-decoration: none;

  }

  .contact-us a:hover {
    transition: .2s ease-in;
    box-shadow: 5px 5px 10px #d98dd3,
      -5px -5px 7px #ffbfff;
  }

  @media screen and (min-width: 700px) {
    footer {
      flex-direction: row;
    }

    footer>div {
      flex: 1 1 200px;
      width: 33%;
      max-width: 300px;
    }
    footer div.contact-us {
        order: 3;
    }

    footer div.logo-container {
        padding-top: 15px;
        order: 2
    }

    .contact-us a {
      margin: 5px 0;
    }
  }

</style>
