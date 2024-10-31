<template>
    <div class="services " id="services" >
      <Header/>
      <section class="hero">
        <no-ssr>

          <carousel
            :loop="true"
            :autoplay="true"
            :nav="false"
            :margin=12
            :responsive="{
              0:{items:1},
              600:{items:1},
              1000:{items:1},
            }">
            <div class="jumbotron jumbotron-fluid" v-for="hero in home.data.hero" :key="hero.title"
              :style="{ background: 'linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)), url( https://api.mallomostudio.com/images/'+ hero.image +')' } "
              >
                <div class="container d-flex h-100 " >
                  <div class="row justify-content-center align-self-center ">
                    <div class="col-sm-12 col-md-12 col-lg-12  align-self-align-self-center text-center ">
                      <h1 class="display-4 text-white" data-aos="fade-up" data-aos-duration="500">{{ hero.title }}</h1>
                      <p data-aos="fade-up" data-aos-duration="1000">
                        {{ hero.description }}
                      </p>
                      <div class="mt-4 foot text-center" data-aos="fade-up" data-aos-duration="2000">
                        <a class="mr-5" href="https://www.instagram.com/mallomo.studio" target="_blank">
                          <font-awesome-icon class="iconstyle" :icon="['fab', 'instagram']"/>
                        </a>
                        <a  href="https://web.facebook.com/profile.php?id=100073342932912" target="_blank">
                          <font-awesome-icon class="iconstyle" :icon="['fab', 'facebook']"/>
                        </a>
                        <a class="ml-5" href="mailto:mallomo.studio@gmail.com" target="_blank">
                          <font-awesome-icon class="iconstyle" :icon="['fas', 'envelope']"/>
                        </a>
                      </div>
                    </div>
                    <nuxt-link class="btn main-button py-3 px-5 mt-4" to="/#portfolio" data-aos="fade-up" data-aos-duration="2000" >Our Projects</nuxt-link>
                    <!-- <button class="btn main-button py-3 px-5 mt-4">Our Projects</button> -->
                  </div>
                </div>
              </div>

          </carousel>

        </no-ssr>

      </section>

      <section class="container text-center" style="margin-top: 80px;" id="service" >
        <div class="row iconservice " data-aos="fade-up" data-aos-duration="500" >
          <div class="col-lg-12 mb-5 ">
            <span class="headingabsolute"><h1 >Our Service</h1></span>
            <h2 >Our <span style="color: #FF6138;">Service</span> </h2>
          </div>
        <div
        v-for="service in home.data.service" :key="service.name"
        class="col-12 col-sm-12 col-md-4 col-lg-4">
          <div class="card text-center" >
            <div class="card-body" >
              <img :src="$axios.defaults.baseURL + '/images/' +service.image" alt="">
                <h5 class=" mt-3 card-title">{{ service.name }}</h5>
                  <p class="card-text">{{ service.description }}</p>
            </div>
          </div>
        </div>
        </div>
      </section>

      <section class="container text-center" style="margin-top: 100px;" id="service" >
        <div class="row iconservice " data-aos="fade-up" data-aos-duration="500" >
          <div class="col-lg-12 mb-5 ">
            <span class="headingabsolute"><h1 >Why Choose Us</h1></span>
            <h2 >Why <span style="color: #FF6138;">Choose Us</span> </h2>
          </div>
          <div
          v-for="service in home.data.service" :key="service.name"
          class="col-12 col-sm-12 col-md-3 col-lg-3">
            <div class="card text-center" >
              <div class="card-body" >
                <img :src="$axios.defaults.baseURL + '/images/' +service.image" alt="">
                  <h5 class=" mt-3 card-title">{{ service.name }}</h5>
                    <p class="card-text">{{ service.description }}</p>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section class="container " style="margin-top: 100px;"  id="visimisi">
        <div class="row">
          <div class="col-12 col-sm-12 col-md-5 col-lg-5 ">
            <img src="../assets/images/aboutimage.png" style="width: 90%;" alt="" data-aos="fade-right" data-aos-duration="500" >
          </div>
          <div class="col-12 col-sm-12 col-md-7 col-lg-7 " data-aos="fade-up" data-aos-duration="500" >
            <h1 style="position: absolute" >Our Vision</h1>
            <h2 >Our <span style="color: #FF6138;">Vision</span> </h2>
            <ul v-for="visi in home.data.visi" :key="visi.name" >
              <li class="text-justify mb-3"> {{ visi.name }} </li>
            </ul>
          </div>
        </div>
      </section>

      <section class="container " style="margin-top: 100px;" >
        <div class="row">
          <div class="col-12 col-sm-12 col-md-7 col-lg-7 " data-aos="fade-up" data-aos-duration="500" >
            <h1 style="position: absolute" >Our Misions</h1>
            <h2 >Our <span style="color: #FF6138;">Misions</span> </h2>
            <ul v-for="misi in home.data.misi" :key="misi.name" >
              <li class="text-justify mb-3"> {{ misi.name }} </li>
            </ul>
          </div>
          <div class="col-12 col-sm-12 col-md-5 col-lg-5 ">
            <img src="../assets/images/aboutimage.png" style="width: 90%;" alt="" data-aos="fade-left" data-aos-duration="500" >
          </div>

        </div>
      </section>

      <section class="container " style="margin-top: 100px;" id="portfolio">
        <div class="row" data-aos="fade-up" data-aos-duration="500" >
          <div class="col-lg-12 mb-5 text-center">
            <span class="headingabsolute"><h1 >Our Portfolio</h1></span>
            <h2 >Our <span style="color: #FF6138;">Portfolio</span> </h2>
          </div>
        </div>
        <div v-if="home.data.portofolio.length > 0" >
          <no-ssr>
            <carousel
                :loop="true"
                :autoplay="true"
                :nav="false"
                :margin=12
                :responsive="{
                  0:{items:1},
                  600:{items:1},
                  1000:{items:1},
                  }">
              <div class="row" v-for="portfolio in home.data.portofolio" :key="portfolio.id">
                <div class="col-12 col-sm-12 col-md-6 col-lg-6 pt-5 " >
                    <h3>{{ portfolio.name }}</h3>
                    <p class="mt-3 mb-4">{{ portfolio.description }}</p>
                    <a :href="portfolio.link" class="btn main-button py-2 px-3">Visit Link</a>

                </div>
                <div class="col-12 col-sm-12 col-md-6 col-lg-6 ">
                    <img :src="$axios.defaults.baseURL + '/images/' +portfolio.image" style="width: 120%; margin-top: -40px" alt="">
                </div>
              </div>
            </carousel>
          </no-ssr>
        </div>
        <div class="row justify-content-center align-self-center " v-else>
          <p>Our Portfolio is Coming Soon...</p>
        </div>
      </section>

      <section>
        <div class="services" style="margin-top:80px">
          <div class="container">
            <div class="row " data-aos="fade-up" data-aos-duration="500" >
              <div class="col-lg-12 mb-5 text-center">
                <span class="headingabsolute"><h1 >Our Product</h1></span>
                <h2 >Our <span style="color: #FF6138;">Product</span> </h2>
              </div>
              <div class="col-sm-6 col-12 col-lg-4 col-md-4 mt-4" >
                <div class="service-item">
                    <div class="imgstyle">
                      <img src="" alt="" />
                    </div>
                  <div class="down-content">
                    <h4 class="mt-2">Gadde POS</h4>
                    <p>
                      Lorem ipsum dolor sit amet consectetur adipisicing elit. Et quia eius dolor quis nisi quisquam. At eaque, placeat ut libero esse, deleniti animi illo
                    </p>
                    <a href="#" class="mybutton">Visit link ></a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section class="container-fluid" style="margin-top: 100px;" id="team">
        <div class="row" data-aos="fade-up" data-aos-duration="500" >
          <div class="col-12 col-sm-12 col-md-12 col-lg-4 team p-5" >
            <h2>Mallomo Studio Team</h2>
            <p class="mt-3 ml-3">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Eum incidunt animi beatae fugit consequatur iure rerum consequatur iure rerum consequatur iure rerum</p>
          </div>

          <div class="col-12 col-sm-12 col-md-12 col-lg-8 sectionteam" >
            <div class="row" >
              <div class="col-12 col-sm-12 col-md-6 col-lg-6 p-0 " v-for="team in home.data.team.slice(0,4)" :key="team.name" >
                <div class="row">
                  <div class="col-6 col-sm-6 col-md-6 col-lg-6">
                    <img :src="$axios.defaults.baseURL + '/images/' +team.image" style="width: 100%" alt="">
                  </div>
                  <div class="col-6 col-sm-6 col-md-6 col-lg-6 detailteam align-self-end " >
                    <h4 class="mb-3 ">{{ team.name }}</h4>
                    <p >{{ team.profession }}</p>
                  </div>
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

  async asyncData({ $axios }) {
    const home = await $axios.$get('/home')
    return { home }
  },

  filters: {
    subStr: function(string) {
      return string.substring(0,65) + ' ...';
    },
  },

  head: {
        title: 'Home Page',
        meta: [
            {
              hid: 'description',
              name: 'description',
              content: 'Meta is coming soon',
            },
            {
              hid: 'title',
              name: 'title',
              content: 'mallomo studio'
            }
        ],
    },
}
</script>

<style scoped>
.jumbotron{
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
    height: 100vh;
    color: #fff;

}

.jumbotron h1 {
  padding-top: 70px;
  font-weight: 800;
  margin-top: 70px;
}

.jumbotron p {
  font-weight: 400;
  line-height: 1.8;
  margin-top: 20px;
  font-size: 17px;
}

p{
  font-weight: 300;
}

.team{
  background-color: #FF6138;
  color: #fff;
}

.sectionteam{
  background-color: #F5F5F5;
}

.detailteam{
  margin-left: -20px;
  padding-left: 20px;
  padding-bottom: 10px;
}

.foot .iconstyle{
  color: #fff;
  font-size: 1.4rem;
}

.animate_delay {
  animation-delay: 0.5s;
}
.boxadvantages {
  padding: 35px;
  border: 1px solid rgb(255, 255, 255);
  transition: all ease 0.75s;
  box-shadow: 0 5px 15px 0 rgba(131, 131, 131, 0.308);
}

.headingabsolute{
  position: absolute;
  margin-left: -160px;
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

.services h3{
  font-size: 2rem;
  font-weight: 600;
}

.iconservice p{
  font-size: 14px;
}

.services .card {
  background: #FFFFFF;
  box-shadow: 10px 10px 20px rgba(168, 168, 168, 0.15), inset -31px -31px 43px rgba(255, 255, 255, 0.65), inset 26px 26px 100px rgba(137, 137, 137, 0.1);
  border-radius: 16px;
  border: 1px rgba(0, 0, 0, 0);
  transition: all 0.7s ease;

}

.services .card img{
  width: 80%;
}

.services .card:hover {
  border : 1px solid #FF6138 ;
}

.service-item p{

  margin-bottom: 20px;
  font-size: 13px;
  color: #575757;
}

.service-item img {
  width: 100%;
  height: 27vh;
  object-fit: cover;
  overflow: hidden;
}

.service-item .imgstyle{
  overflow: hidden;
}

.service-item .down-content {
  background-color: #f7f7f7;
  padding: 30px;
}

.services .service-item {
    margin-bottom: 30px;

}


.service-item .down-content h4 {
  font-size: 20px;
  font-weight: 700;
  letter-spacing: 0.25px;
  margin-bottom: 15px;
}
</style>

