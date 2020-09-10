<template>
    <header class="page-hader wrapper">
      <h1><nuxt-link to="/"><img class="logo" src="~/assets/images/SERPENT_FIX.png" alt="SERPENTホーム" /></nuxt-link></h1>
      <nav>
        <ul class="main-nav">
          <li><nuxt-link to="/about">About</nuxt-link></li>
          <li><nuxt-link to="/member">Member</nuxt-link></li>
          <li><nuxt-link to="/news">News</nuxt-link></li>
          <li><nuxt-link to="/blog">Blog</nuxt-link></li>
          <li><nuxt-link to="/contact">Contact</nuxt-link></li>
          <li><nuxt-link to="/privacy">Privacy Policy</nuxt-link></li>
        </ul>
      </nav>
    </header>
</template>

<script>
    export default {
        name: "Header"
    }
</script>

<style scoped>
  a {
    text-decoration: none;
  }
  img {
    max-width: 100%;
  }
  .logo {
    width: 250px;
    margin-top: 14px;
  }
  li {
    list-style: none;
  }
  .main-nav {
    display: flex;
    font-size: 1.25rem;
    text-transform: uppercase;
    margin-top: 34px;
    list-style: none;
  }
  .main-nav li {
    margin-left: 36px;
  }
  .main-nav a {
    color: #432;
  }
  .main-nav a:hover {
    color: #0bd;
  }
  .page-hader {
    display: flex;
    justify-content: space-between;
  }
  .wrapper {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 4%;
  }
</style>
