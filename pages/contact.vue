<template>
    <div class="services " id="services" >
      <Header/>
      <section class="hero ">
          <div class="jumbotron jumbotron-fluid  ">
            <div class="container d-flex h-100 ">
              <div class="row justify-content-center align-self-center mt-5">
                <div class="col-sm-12 col-md-12 col-lg-12  text-left animate__animated animate__slideInUp ">
                  <h2 class="display-4 text-white">Contact Us</h2>
                  <p>
                    Lorem ipsum dolor, sit amet consectetur adipisicing elit. Maiores, consequuntur quidem? Beatae maiores quos quas repudiandae explicabo placeat, dolores eos consequatur enim 
                  </p>
                </div> 
              </div>
            </div>
          </div>
      </section>

      <section class="container text-left" style="margin-top: 80px;" >
        <div class="row iconservice "  v-for="contact in contacts.data.contact"  :key="contact.id" >
          <div class="col-12 col-sm-12 col-md-4 col-lg-4"  >
            <div class="card " data-aos="fade-up" data-aos-duration="2000">
              <div class="card-body p-5" >
                <font-awesome-icon class="iconstyle" :icon="['fab', 'instagram']"/>
                <h5 class=" mt-4 mb-3 card-title">Contact Us</h5>
                <p class="card-text">{{ contact.instagram }}</p>
              </div>
            </div>
          </div>
          <div class="col-12 col-sm-12 col-md-4 col-lg-4">
            <div class="card " data-aos="fade-up" data-aos-duration="2000">
              <div class="card-body p-5" >
                <font-awesome-icon class="iconstyle" :icon="['fas', 'map-marked-alt']"/>
                <h5 class=" mt-4 mb-3 card-title">Office Address</h5>
                <p class="card-text">{{ contact.address }}</p>
              </div>
            </div>
          </div>
          <div class="col-12 col-sm-12 col-md-4 col-lg-4"  >
            <div class="card " data-aos="fade-up" data-aos-duration="2000">
              <div class="card-body p-5" >
                <font-awesome-icon class="iconstyle" :icon="['fas', 'phone-alt']"/>
                <h5 class=" mt-4 mb-3 card-title">Telephone</h5>
                <p class="card-text">{{ contact.phone }}</p>
              </div>
            </div>
          </div> 
        </div>
      </section>

       <section class="container " style="margin-top: 100px;" >
        <div class="row">
          <div class="col-12 col-sm-12 col-md-12 col-lg-12">
            <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d15894.629603445477!2d119.47396822288488!3d-5.158706340102852!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2dbee315e9a66cbd%3A0x213367768c56527b!2sAntang%2C%20Manggala%2C%20Makassar%20City%2C%20South%20Sulawesi!5e0!3m2!1sen!2sid!4v1632884851955!5m2!1sen!2sid" width="100%" height="450vh" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
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
    const contacts = await $axios.$get('/contact')
    return { contacts }
  },
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

.iconstyle{
  color: #FF6138;
  font-size: 3rem;
}
.services h1{
  font-size: 3.5rem;
  -webkit-text-fill-color: white;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: rgba(0, 0, 0, 0.212);
}

.mybutton{
  background-color: #FF6138;
  border-radius: 5px;
  color: #fff;
  font-size: 14px;
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


.contact-us {
  background-color: #141733 !important;
  /* padding: 0 !important; */
}

.contact-us h2{
  color: #fff;
  font-weight: 700;
}


.callback-form .contact-form input {
  border-radius: 6px;  
  display: inline-block;
  padding: 0px 15px;
  color: #6a6a6a;
  font-size: 13px;
  border: none;
  margin-bottom: 20px;
}


.callback-form .contact-form textarea {
  border-radius: 6px;
  padding: 15px;
  color: #6a6a6a;
  font-size: 13px;
  border: none;
  margin-bottom: 35px;
}

.callback-form .contact-form ::-webkit-input-placeholder, .callback-form .contact-form :-ms-input-placeholder,.callback-form .contact-form ::placeholder {
  /* Edge */
  color: #aaa;
}
</style>

<<<<<<< HEAD

=======
>>>>>>> e6bddea3b0f3903398051301a465e4e2615b66ca


