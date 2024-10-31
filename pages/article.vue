<template>
    <div class="services " id="services" >
      <Header/>
      <section class="hero ">
          <div class="jumbotron jumbotron-fluid  ">
            <div class="container d-flex h-100 ">
              <div class="row justify-content-center align-self-center mt-5">
                <div class="col-sm-12 col-md-12 col-lg-12  text-left animate__animated animate__slideInUp ">
                  <h2 class="display-4 text-white">Article</h2>
                  <p>
                    Lorem ipsum dolor, sit amet consectetur adipisicing elit. Maiores, consequuntur quidem? Beatae maiores quos quas repudiandae explicabo placeat, dolores eos consequatur enim 
                  </p>
                </div> 
              </div>
            </div>
          </div>
      </section>

      <div class="services" style="margin-top:100px">
        <div class="container">
          <div class="row ">
            <div class="col-sm-6 col-12 col-lg-4 col-md-4 mt-4" v-for="article in articles.data.article" :key="article.id">
              <div class="service-item">
                  <div class="imgstyle">
<!--                    TODO all the source of image should be from object of response-->
                    <img :src="$axios.defaults.baseURL + '/images/' + article.image" alt="" />
                  </div>
                <div class="down-content">
                  <span>{{ article.created_at }}</span>
                  <h4 class="mt-2">{{ article.name }}</h4>
                  <p>
                    {{ article.description | subStr }}
                  </p>
                  <nuxt-link :to="`/detailarticle/${article.id}`" class="mybutton">Read full post ></nuxt-link>
                  <!-- <nuxt-link :to=" path: '/detailarticle/' + slug, query: {id: `${article.id}`}  " class="mybutton">Read full post ></nuxt-link> -->
                </div>
              </div>
            </div>
            
          </div>
          
        </div>
      </div>
      
      <Footer/>

    </div>

</template>

<script>
export default {
  layout: 'default',
  async asyncData({ $axios }){
    const articles = await $axios.$get('/article')
    return { articles }

  },
  filters: {
    subStr: function(string) {
      return string.substring(0,65) + ' ...';
    },
  },
  head() {
    for (let index = 0; index < this.articles.data.article.length; index++) {
      return{
        title: 'article',
        meta: [
          {
            hid: 'description',
            name: 'description',
            content: this.articles.data.article[index].description,
          },
        ]
      }
    }
  }
}
</script>

<style scoped>
.jumbotron{
  /* background: linear-gradient(to right, #0d81cede, #0d81ce60),
          url('../static/happy-business-people-celebrating-success-at-N5XSH86-e1572946215297.jpg'); */
    background: url('../static/happy-business-people-celebrating-success-at-N5XSH86-e1572946215297.jpg');
      -webkit-background-size: cover;
      -moz-background-size: cover;
      -o-background-size: cover;
    background-size: cover;
    height: 70vh;
    color: #fff;
    
    
}
.jumbotron h2 {
  /* padding-top: 120px; */
  font-weight: 700;
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

.service-item span{
  color: #929292;
  font-size: 15px;
}

.iconstyle{
  color: #FF6138;
  font-size: 4rem;
}
.services h1{
  font-size: 3.5rem;
  -webkit-text-fill-color: white;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: rgba(0, 0, 0, 0.212);
}

.mybutton{
  color: #FF6138;
  font-size: 15px;
  margin-bottom: 20px;
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
  width: auto;
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
<<<<<<< HEAD
=======

>>>>>>> e6bddea3b0f3903398051301a465e4e2615b66ca
