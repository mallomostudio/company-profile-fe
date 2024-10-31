<template>
    <div class="services " id="services" >
      <header>
        <nav class=" navbar navbar-expand-lg shadow-sm bg-white fixed-top py-3" id="mainNav">
          <div class="container-fluid px-4 py-1" >
            <!-- <a class="navbar-brand js-scroll-trigger" href="#page-top" style="font-size: 16px;">LOGO</a> -->
            <h6 class="navbar-brand">Logo</h6>
            <button class="navbar-toggler navbar-toggler-right" type="button" data-toggle="collapse" data-target="#navbarResponsive" aria-controls="navbarResponsive" aria-expanded="false" aria-label="Toggle navigation">
              <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse " id="navbarResponsive">
              <ul class="navbar-nav mx-auto ">
                <li class="nav-item">
                  <a class="nav-link js-scroll-trigger" href="#services">Home</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link js-scroll-trigger" href="#portfolio">Service</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link js-scroll-trigger" href="#portfolio">Visi Misi</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link js-scroll-trigger" href="#portfolio">Our Team</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link js-scroll-trigger" href="#portfolio">Article</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link js-scroll-trigger" href="#portfolio">Portfolio</a>
                </li>
                
              </ul>
              <button class="btn main-button py-3 px-4">Contact Us</button>
            </div>
          </div>
        </nav>
      </header>

      <section style= "margin-top: 150px">
        <div class="container ">
          <div class="row maincontent">
            <div class="col-lg-12 text-center mb-5">
              <h2 class="mt-2">{{ article.data.name }}</h2>
            </div>
            <div class="col-sm-12 col-12 col-lg-md-8 col-lg-8 foot service-item">
              <div class="row">
                <h6 class="mr-3 ml-3">Share this post : </h6>
                      <a class="mr-3" href="https://www.linkedin.com/in/ayuramadhann/" target="_blank">
                        <font-awesome-icon class="iconstyle" :icon="['fab', 'linkedin']"/>
                      </a>
                      <a class="mr-3" href="https://dribbble.com/ayuramadhann" target="_blank">
                        <font-awesome-icon class="iconstyle" :icon="['fab', 'github']"/>
                      </a>
                      <a  href="https://api.whatsapp.com/send?phone=6282393633155" target="_blank">
                        <font-awesome-icon class="iconstyle" :icon="['fab', 'facebook']"/>
                      </a>
                      <a class="ml-3" href="mailto:ayut.ramadhan@gmail.com" target="_blank">
                        <font-awesome-icon class="iconstyle" :icon="['fas', 'envelope']"/>
                      </a>
              </div>
              <img :src="$axios.defaults.baseURL + '/images/' + article.data.image" class="w-100 mt-4 mb-4" alt="">
              <span >{{ article.data.created_at }}</span>
              <p class="mt-3" >{{ article.data.description }}</p>
            </div>
            <div class="col-sm-12 col-12 col-lg-md-4 col-lg-4 service-item" > 
              <h5>New Article</h5>
              <div class="row mt-3" v-for="newarticle in newarticles.data.article.slice(0,5)" :key="newarticle.id" >
                <div class="col-sm-3 col-3 col-md-3 col-lg-3 ">
                  <img :src=" $axios.defaults.baseURL + '/images/' + newarticle.image"  alt="" />
                </div>
                <div class="col-sm-8 col-8 col-md-8 col-lg-8 ">
                  <h6>{{ newarticle.name }}</h6>
                </div>
              </div>

            </div>
          </div>
        </div>
      </section>
      
      <Footer/>

    </div>

</template>

<script>
export default {
  layout: 'default',
  async asyncData ({ $axios, params }){
    const article = await $axios.$get('/detail-article/' + params.id)
    const newarticles = await $axios.$get('/article')
    return { article, newarticles }
  },
  head() {
      return{
        title: 'article',
        meta: [
          {
            hid: 'description',
            name: 'description',
            content: this.article.data.description,
          },
        ]
      }
  }
}
</script>

<style scoped>
header #mainNav .navbar-nav .nav-item .nav-link {
  color: rgb(0, 0, 0);
  font-weight: 400;
  font-size: 1.1rem;
  padding: 0 1.5rem 0;
}

.maincontent img{
  border-radius: 9px;
}

.foot .iconstyle{
  color: #3f3f3f;
  font-size: 1.2rem;
}

.services h1{
  font-size: 3.5rem;
  -webkit-text-fill-color: white;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: rgba(0, 0, 0, 0.212);
}
.services h2{
  font-size: 2.8rem;
  font-weight: 600;
  padding-left: 10px;
  margin-top: 20px;
  position: relative;
}

.service-item span{
  color: #929292;
  font-size: 15px;
}

.services h3{
  font-size: 2rem;
  font-weight: 600;
}

.iconservice p{
  font-size: 14px;
}

.service-item img {
  width: 110%;
  border-radius: 5px;
}

</style>




