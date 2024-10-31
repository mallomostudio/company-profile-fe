 <template>
  <section style="margin-top:100px">
    <footer>
      <div class="container">
        <div class="row">
          <div class="col-md-3 footer-item">
            <h4>Mallomo Studio</h4>
            <p>
              Lorem ipsum, dolor sit amet consectetur adipisicing elit. Enim molestias ullam illo distinctio, quisquam veniam fugiat dolores saepe 
            </p>
          </div>
          <div class="col-md-3 footer-item">
            <h4>Article</h4>
            <ul class="menu-list">
              <li class="nav-item">
                <nuxt-link class="nav-link js-scroll-trigger" to="/#service" >Service</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link class="nav-link js-scroll-trigger" to="/#visimisi" >Visi Misi</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link class="nav-link js-scroll-trigger" to="/#team" >Our Team</nuxt-link>
              </li>
            </ul>
          </div>
          <div class="col-md-3 footer-item">
            <h4>Daftar Halaman</h4>
            <ul class="menu-list">
              <li class="nav-item">
                <nuxt-link class="nav-link js-scroll-trigger" to="/#service" >Service</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link class="nav-link js-scroll-trigger" to="/#visimisi" >Visi Misi</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link class="nav-link js-scroll-trigger" to="/#team" >Our Team</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link class="nav-link js-scroll-trigger" to="/article">Article</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link class="nav-link js-scroll-trigger" to="/#portfolio"  >Portfolio</nuxt-link>
              </li>
            </ul>
          </div>
          <div class="col-md-3 footer-item">
            <h4>IT Service</h4>
            <ul class="menu-list">
              <li class="nav-item">
                Web Development
              </li>
              <li class="nav-item">
                Mobile Development
              </li>
              <li class="nav-item">
                Desktop Development
              </li>
            </ul>
          </div>
        </div>
      </div>
    </footer>
    <div class="sub-footer">
      <div class="container">
        <div class="row">
          <div class="col-md-12">
            <p>
              Copyright &copy; 2021 Mallomo Studio
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>

footer {
  background-image: linear-gradient(90deg,#282f4d 0%,#18172e 100%);
  padding: 80px 0px;
  color: #fff;
}

footer h4 {
  color: #fff;
  font-size: 20px;
  font-weight: 600;
  letter-spacing: 0.25px;
  margin-bottom: 35px;
}
footer p {
  color: #fff;
}

footer ul.social-icons {
  margin-top: 25px;
}

footer ul.social-icons li {
  display: inline-block;
  margin-right: 5px;
}

footer ul.social-icons li:last-child {
  margin-right: 0px;
}

footer ul.social-icons li a {
  width: 34px;
  height: 34px;
  display: inline-block;
  line-height: 34px;
  text-align: center;
  background-color: #fff;
  color: #232323;
  border-radius: 50%;
  transition: all 0.3s;
}

footer ul.social-icons li a:hover {
  background-color: #51cae6;
}

footer ul.menu-list li {
  margin-bottom: 13px;
}

footer ul.menu-list li:last-child {
  margin-bottom: 0px;
}

footer ul.menu-list li a {
  font-size: 14px;
  color: #fff;
  transition: all 0.3s;
}

footer ul.menu-list li a:hover {
  color: #51cae6;
}


/* Sub-footer Style */

.sub-footer {
  background-image: linear-gradient(90deg,#282f4d 0%,#18172e 100%);
  text-align: center;
}

.sub-footer p {
  color: #fff;
  font-weight: 300;
  letter-spacing: 0.5px;
}

.sub-footer a {
  color: #fff;
}


</style>


