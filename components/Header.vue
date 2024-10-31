<template>
    <header>
      <nav @scroll="onScroll" class=" navbar navbar-expand-lg navbar-dark fixed-top py-3 px-4 py-1" id="mainNav">
        <h6 class="navbar-brand text-light">Malomo Std</h6>
          <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav mx-auto">
              <li class="nav-item">
                <nuxt-link class="nav-link js-scroll-trigger" to="/">Home</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link class="nav-link js-scroll-trigger" to="/#service" >Service</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link class="nav-link js-scroll-trigger" to="/#visimisi" >Visi Misi</nuxt-link>
              </li>
                            <li class="nav-item">
                <nuxt-link class="nav-link js-scroll-trigger" to="/#portfolio" >Portfolio</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link class="nav-link js-scroll-trigger" to="/#team" >Our Team</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link class="nav-link js-scroll-trigger" to="/article">Article</nuxt-link>
              </li>
            </ul>
            <nuxt-link class="btn main-button py-3 px-4" to="/contact">Contact Us</nuxt-link>
          </div>
        </nav>
    </header>
</template>

<script>
export default {
  methods: {
    onScroll (event) {
      let header = document.querySelector(".navbar");
        if (window.scrollY > 50 ) {
          header.classList.add("mynav","navbar-light");
          header.classList.remove("navbar-dark");
        }else{
          header.classList.remove("mynav", "navbar-light");
        }
    },
  },
  created () {
    window.addEventListener('scroll', this.onScroll);
  },
}
</script>

<style scoped>
  .navbar-toggler {
    border-color: rgb(221, 221, 221);
  }
</style>
