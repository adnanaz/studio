<template>
  <v-card class="overflow-hidden">
    <!-- NAVBAR -->
    <v-app-bar
      absolute
      color="white"
      elevate-on-scroll
      scroll-target="#scrolling-techniques-7"
    >
    
    <div
        style="width: 100%"
        :class="$vuetify.breakpoint.mdAndDown ? 'd-flex ' : 'd-none'"
      >
        <v-toolbar-title class="d-flex align-center ml-3">
          <img
            style="width: 100px"
            :src="require('@/assets/images/logo.png')"
            alt="logo higlob"
          />
        </v-toolbar-title>
        <v-spacer></v-spacer>

        <v-app-bar-nav-icon @click.stop="drawer = !drawer" class="mr-0" 
          ><img :src="require('@/assets/images/bar-chart.png')" alt="btn-toggle-navbar"
        /></v-app-bar-nav-icon>
    </div>
      <v-toolbar-title  :class="$vuetify.breakpoint.mdAndDown ? 'd-none' : ' d-flex'" class="nav__pa-left"
            ><v-img :src="require('@/assets/images/logo.png')"></v-img>
      </v-toolbar-title>

      <v-spacer></v-spacer>
      <div :class="$vuetify.breakpoint.mdAndDown ? 'd-none' : ' d-flex'" class=" d-flex justify-center align-center nav__pa-right">
        <ul class="d-flex">
          <li><NuxtLink class="navbar__item" to="/">Work</NuxtLink></li>
          <li><NuxtLink class="navbar__item" to="/about">About</NuxtLink></li>
          <li><NuxtLink class="navbar__item" to="/contact">Contact</NuxtLink></li>
        </ul>
      </div>
      
    </v-app-bar>

    <!-- NAVBAR MOBILE  -->
    <v-navigation-drawer
      v-model="drawer"
      absolute
      temporary
    >
      <v-list
        nav
        dense
      >
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
          <v-list-item>
            <v-list-item-title>Foo</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-title>Bar</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-title>Fizz</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-title>Buzz</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <!-- CONTENT -->
    <v-sheet
      id="scrolling-techniques-7"
      class="overflow-y-auto"
      max-height="100vh"
    >
        <!-- SECTION 1 - HERO -->
        <section class="hero">
          <v-row class="ma-0">
            <v-col cols="12" class="pa-0" xs="12" sm="12" md="8" lg="8" xl="8">
              <!-- <div data-aos="fade-up"
              data-aos-offset="200"
              data-aos-delay="50"
              data-aos-duration="1500"
              data-aos-anchor-placement="top-center"> -->
              <div class="hero__text">
              <h1>Developing your <br v-show="$vuetify.breakpoint.xl ? true : false"> Website is  Our <br v-show="$vuetify.breakpoint.xl ? true : false"> Solution.</h1>

              <h4>Working with our team can develop <br v-show="$vuetify.breakpoint.smAndDown ? true : false"> your website even better</h4>
              <div class="btn">
                <v-hover  v-slot="{ hover }">
                <v-btn :width="$vuetify.breakpoint.xs ? '104px' : '150'" :small="$vuetify.breakpoint.xs ? true : false"  elevation="0"  :style="
                      hover
                        ? 'box-shadow: #FFCD94 0px 4px 12px !important'
                        : ''
                    "  rounded class="white--text font-weight-regular text-capitalize hero__btn" >
                  Lets Talk
                  <v-icon class="white--text" right>mdi-arrow-right</v-icon>
                </v-btn>
                </v-hover>
              </div>
            </div>
              <!-- </div> -->

            <v-row class="ma-0">
            <v-col cols="12" class="illu__books">
                <div >
                <img width="20vh":src="require('@/assets/images/buku.png')">
              </div>
            </v-col>
            </v-row>
            </v-col>
            
            <v-col cols="12" xs="12" sm="12" md="4" lg="4" xl="4" class="illu__hero pa-0">
              <div class="" >
                <!-- <div data-aos="fade-down"
              data-aos-offset="200"
              data-aos-delay="50"
              data-aos-duration="1500"
              data-aos-anchor-placement="top-center"> -->
                <img :src="require('@/assets/images/hero-move.svg')" >
                <!-- </div> -->
              </div>
            </v-col>
          </v-row>
        </section>
        <!-- SECTION 2 - SERVICES -->
        <section class="services">
          <v-row class="services__wrap ma-0">
            <v-col cols="12" xs="12" sm="12" md="4" lg="5" xl="6" class="services__hero">
              <div class="services__hero-div">
              <h2>
                The services we will use <br v-show="$vuetify.breakpoint.smAndDown ? false : true">
                to build your project
              </h2>
              <span>
                The result of trust from our customers who have <br v-show="$vuetify.breakpoint.xs ? false : true">
                used the services of our team
              </span>
              </div>
            </v-col>
            <v-col class="pa-0" cols="12" xs="12" sm="12" md="8" lg="7" xl="6">
              <div class="d-flex align-center flex-wrap" :class="$vuetify.breakpoint.smAndDown ? 'justify-center' : 'justify-start'">
                <v-hover v-for="(el, idx) in card_services" :key="idx" v-slot="{ hover }">
                <v-card   class="services__card rounded-xl" :style="
                        hover
                          ? 'box-shadow: 2px 7px 26px rgba(0, 0, 0, 0.20);'
                          : 'box-shadow: 2px 7px 26px rgba(0, 0, 0, 0.00);'
                      ">
                    <v-card-title class="services__card-title"> 
                      <img class="mr-2"  :src="require(`@/assets/images/icon-card/${el.img_url}`)" :alt="el.img_alt"> 
                      {{el.title}}
                    </v-card-title>
                      <div class="services__card-subtitle">
                        {{el.description}}
                      </div>
                </v-card>
                </v-hover>
              </div>
            </v-col>
          </v-row>
        </section>
        <!-- SECTION 3 - PROJECTS -->
        <section class="projects">
          <v-row class="ma-0">
            <!-- HERO -->
            <v-col cols="12" style="padding:0">
              <div class="projects__wrap d-flex  flex-wrap align-center" :class="$vuetify.breakpoint.smAndDown ? 'justify-start' : 'justify-center'">
                <div class="projects__hero">
                <h1>The work of our team, from several clients</h1>
                <p>The result of trust from our customers who have used the services of our team</p>
              </div>
              </div>
              <v-container>
              <v-img class="projects__img-slash" :src="require('@/assets/images/project-slash.svg')"></v-img>
              </v-container>
            </v-col>
            <!-- PROJECT PREVIEW -->
            <v-col cols="12" class="preview">
              <v-container>
              <div class="d-flex flex-wrap" :class="$vuetify.breakpoint.smAndDown ? 'justify-center' : 'justify-center'">
              <v-card  v-for="(el,index) in card_portofolio" :key="index"
                elevation="0"
                :loading="loading"
                class="preview__card my-7"
                >
                <template slot="progress">
                  <v-progress-linear
                    color="deep-purple"
                    height="10"
                    indeterminate
                  ></v-progress-linear>
                </template>

                <v-img class="preview__card-img"
                  :src="require(`@/assets/images/portofolio/${el.img_url}`)"
                ></v-img>

                <!-- <v-card-title class="preview__card-title">
                  <h3>{{el.title}}</h3> 

                  <v-spacer v-show="$vuetify.breakpoint.xs ? false : true"></v-spacer>

                <div class="technology d-flex justify-start align-center flex-row flex-wrap" v-for="(item, idx) in el.tech_img">
                  <v-img class="technology__img" :src="require(`@/assets/images/portofolio/tech/${item}.png`)"></v-img>
                </div>
              </v-card-title> -->


              <v-card-title class="preview__card-title ">
                <h3>{{el.title}}</h3>
              </v-card-title>
                <div class="d-flex align-center" >
              <div class="technology" v-for="(item, idx) in el.tech_img" :key="idx">
                  <img class="technology__img"  :src="require(`@/assets/images/portofolio/tech/${item}.png`)">
                </div> 
              </div>

              <v-card-actions class="preview__card-action">
                <v-btn
                  color="deep-purple lighten-2"
                  text
                  :href="el.url_link"
                  target="_blank"
                  class="font-italic font-weight-bold text-capitalize"
                >
                  Visit Site
                </v-btn>
              </v-card-actions>
              </v-card>
              </div>
              </v-container>
            </v-col>
          </v-row>
        </section>

        <!-- SECTION 4 - HERO 2 ADVERTISEMENT -->
        <section style="background:#F0F3FF;" class="advertisement">
          <v-row class="ma-0 advertisement__row">
            <v-col cols="12" sm="12" md="5" lg="5" xl="5" class="advertisement__wrap pa-0 order-2 order-sm-2 order-md-1" >
              <v-img class="advertisement__img" :src="require('@/assets/images/hero-hai.svg')"></v-img>
            </v-col>
            <v-col cols="12" sm="12" md="7" lg="7" xl="7" style="position:relative;" class="d-flex justify-start my-auto flex-column pa-0 order-1 order-sm-1 order-md-2">
            <div class="advertisement__hero">
                <h1>Everyday our team develops <br> customer products.</h1>
                <p>Our team's process is focused on designing and developing <br>products from our clients</p>
                <v-img  style="width:250px;" :src="require('@/assets/images/slash-hero-2.svg')"></v-img>
            </div>
            </v-col>
          </v-row>
        </section>

        <!-- SECTION 5 - HERO COLAB -->
        <section class="colab">
          <v-row  class="ma-0">
            <v-col cols="12" xs="12" sm="12" md="6" lg="6" xl="6"  class="d-flex align-center colab__left ">
              <div class="colab__title">
                <h1>
                  Collaboration between <br v-show="$vuetify.breakpoint.xs ? false : true"> our team
                </h1>
                <p>Our team believes that building a website is a cultural <br>
                relationship between companies and customers for 
                the better</p>
              </div>
            </v-col>
            <v-col cols="12" xs="12" sm="12" md="6" lg="6" xl="6"  class="colab__right">
              <v-img class="colab__img" :src="require('@/assets/images/collaboration.svg')"></v-img>
            </v-col>
            
            <!-- GAMBAR BUILDING WEBSITE -->
            <v-col class="colab__img-hero" cols="12" align="center" justify="center">
              <v-img :src="$vuetify.breakpoint.xs ? require('@/assets/images/mobile-building-img.png') : require('@/assets/images/building-website.svg')"></v-img>
            </v-col>
          </v-row>
        </section>

        <!-- SECTION 6 - OUR TECHNOLOGY -->
        <section class="ourtech" style="background:#F0F3FF">
          <v-row  class="ma-0">
            <v-col class="pa-0" cols="12">
              <div class="ourtech__title">
              <h1>
                  Our Technology in <br v-show="$vuetify.breakpoint.xs ? true : false">  Developing <br v-show="$vuetify.breakpoint.xs ? false : true"> Your Website
              </h1>
              </div>
              <div  class="ourtech__item d-flex justify-center  flex-wrap align-center">
                  <div v-for="(el, idx) in technology_we_used" :key="idx" class="ourtech__img-wrap">
                    <img :src="require(`@/assets/images/technology/${el.img_src}`)" :alt="el.img_alt"></img>
                  </div>
              </div>
            </v-col>
          </v-row>
        </section>

        <!-- FOOTER -->
        <section class="footer pa-0">
          <v-card  color="#F0F3FF" elevation="0" height="442" class="footer__card d-flex  flex-column">
            <div class="footer__card-title my-auto">
              <h1>When you need <br v-show="$vuetify.breakpoint.xs ? false : true"> project contact us</h1>
                <div class="btn">
                <v-hover  v-slot="{ hover }">
                <v-btn width="150"  elevation="0"  :style="
                      hover
                        ? 'box-shadow: #FFCD94 0px 4px 12px !important'
                        : ''
                    " style="height:50px; background: linear-gradient(94.5deg, #FE8D0D -7.68%, #EEB00F 109.25%); " rounded class="white--text font-weight-regular text-capitalize footer__btn" >
                  Lets Talk
                  <v-icon class="white--text" right>mdi-arrow-right</v-icon>
                </v-btn>
                </v-hover>
              </div>
            </div>

          
          </v-card>
        </section>
    </v-sheet>
  </v-card>
</template>


<script>
export default {
  data: () => ({
    drawer: false,
    group: null,

    loading: false,
    card_services: [
      {
        img_url: '1.png',
        title: 'Grow Your Bussiness',
        img_alt: 'icon image grow your bussiness',
        description: 'grow your business by creating the perfect website',
      },
      {
        img_url: '2.png',
        title: 'Bussiness Real Time Report',
        img_alt: 'icon Bussiness Real Time Report',
        description: 'serve the making of your report program in real time',
      },
      {
        img_url: '3.png',
        title: 'Automate your business',
        img_alt: 'Automate your business',
        description: 'Serving automation to develop your project',
      },
      {
        img_url: '4.png',
        title: 'Upgrade your website',
        img_alt: 'Upgrade your website',
        description:
          'Our job is to help you develop a better experiences website',
      },
    ],
    card_portofolio: [
      {
        title: 'PT. Higlob Sinar Utama',
        img_url: 'higlob.png',
        tech_img: ['icon-figma', 'icon-nuxt', 'icon-mysql', 'icon-sass'],
        url_link: 'https://www.higlob.id/',
      },
      {
        title: 'Higlob Studio',
        img_url: 'studio.png',
        tech_img: ['icon-figma', 'icon-nuxt', 'icon-mysql', 'icon-sass'],
        url_link: 'https://www.higlob.id/',
      },
    ],
    technology_we_used: [
      {
        img_src: 'figma.png',
        img_alt: 'logo-Figma',
      },
      {
        img_src: 'html.png',
        img_alt: 'logo-Html',
      },
      {
        img_src: 'css.png',
        img_alt: 'logo-CSS',
      },
      {
        img_src: 'js.png',
        img_alt: 'logo-Javascript',
      },
      {
        img_src: 'vue.png',
        img_alt: 'logo-Vue',
      },
      {
        img_src: 'firebase.png',
        img_alt: 'logo-Firebase',
      },
      {
        img_src: 'mysql.png',
        img_alt: 'logo-Mysql',
      },
      {
        img_src: 'laravel.png',
        img_alt: 'logo-Laravel',
      },
      {
        img_src: 'bootstrap.png',
        img_alt: 'logo-Boostrap',
      },
      {
        img_src: 'sass.png',
        img_alt: 'logo-Sass',
      },
      {
        img_src: 'nuxt.png',
        img_alt: 'logo-Nuxt',
      },
    ],
  }),
  watch: {
    group() {
      this.drawer = false
    },
  },
  mounted() {},
}
</script>


<style lang="scss">
//shadow navbar desktop
.v-sheet.v-app-bar.v-toolbar:not(.v-sheet--outlined) {
  box-shadow: 0px 2px 4px -1px rgb(0 0 0 / 0%), 0px 4px 5px 0px rgb(0 0 0 / 10%),
    0px 14px 4px rgb(0 0 0 / 4%);
}

$red: #f37272;
$duration: 0.5s;
$distance: 8px;
$easeOutBack: cubic-bezier(0.175, 0.885, 0.32, 1.275);

.navbar {
  &__item {
    color: #2e186a;
  }
}

ul {
  list-style-type: none;
  margin: 0;
  text-align: center;

  li {
    display: inline-block;
    margin: 0 15px;
  }

  a {
    font-size: 16px;
    color: #2e186a !important;
    position: relative;
    text-transform: capitalize;
    text-decoration: none;
    padding-bottom: 5px;

    &:before,
    &:after {
      content: '';
      position: absolute;
      bottom: 2px;
      left: 0;

      right: 0;
      height: 3px;
      background-color: $red;
    }
    &:before {
      opacity: 0;
      transform: translateY(-$distance);
      transition: transform 0s $easeOutBack, opacity 0s;
    }
    &:after {
      opacity: 0;
      transform: translateY($distance/2);
      transition: transform $duration $easeOutBack, opacity $duration;
    }
    &:hover {
      &:before,
      &:after {
        opacity: 1;
        transform: translateY(0);
      }
      &:before {
        transition: transform $duration $easeOutBack, opacity $duration;
      }
      &:after {
        transition: transform 0s $duration $easeOutBack, opacity 0s $duration;
      }
    }
  }
}

/* exact link will show the primary color for only the exact matching link */
a.nuxt-link-exact-active {
  font-weight: 600;
}

// MEDIA QUERY
@media screen and (min-width: 300px) and (max-width: 600px) {
  // shadow navbar mobile
  .v-sheet.v-app-bar.v-toolbar:not(.v-sheet--outlined) {
    box-shadow: 0px 2px 4px -1px rgb(0 0 0 / 0%),
      0px 4px 5px 0px rgb(0 0 0 / 10%), 0px 14px 4px rgb(0 0 0 / 2%);
  }

  .hero {
    margin-top: 5rem;
    &__text {
      margin-left: 0;
      padding: 1rem;

      h1 {
        color: #2e186a;
        font-family: $font-inter;
        font-weight: 700;
        font-size: 48px;
        line-height: 60px;
        margin-bottom: 1.5rem;
      }

      h4 {
        font-style: normal;
        font-weight: 400;
        font-size: 14px;
        line-height: 25px;
      }
    }
    .btn {
      margin-top: 2rem;
    }

    .illu__hero {
      position: relative;
      float: right;
      height: 330px;

      img {
        position: absolute;
        width: calc(100vh - 360px);
        top: -107px;
        right: 0;
      }
    }
  }

  // SERVICES
  .services {
    padding: 1rem;
    &__wrap {
      // padding: 1rem;
      margin-left: 0;
      margin-top: 0rem;
    }

    &__hero {
      padding: 0;
      margin-top: 1rem;
      margin-bottom: 2rem;
      h2 {
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 24px;
        line-height: 35px;
        /* or 146% */

        letter-spacing: 0.003em;

        /* FONT COLOUR */

        color: #2e186a;
      }

      span {
        font-style: normal;
        font-weight: normal;
        font-size: 14px;
        line-height: 28px;
        /* or 200% */
        letter-spacing: 0.003em;
        color: #828282;
      }
    }

    &__card {
      // margin: 10px;
      padding: 16px;
      &-title {
        padding: 5px;
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 18px;
        line-height: 22px;
        /* identical to box height, or 122% */
        text-align: center;
        letter-spacing: 0.003em;
      }

      &-subtitle {
        padding: 5px;
        font-family: $font-inter;
        font-style: normal;
        font-weight: normal;
        font-size: 13px;
        line-height: 18px;
        /* or 138% */
        text-align: left;
        letter-spacing: 0.003em;

        color: #828282;
      }
    }
  }

  //PROJECTS
  .projects {
    margin-top: 0rem;
    padding: 1rem;

    &__img {
      width: 10vh;
    }

    &__hero {
      text-align: left;
      h1 {
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 24px;
        line-height: 35px;
        /* or 146% */
        letter-spacing: 0.003em;
        /* FONT COLOUR */
        color: #2e186a;
      }

      p {
        margin-top: 1rem;
        font-style: normal;
        font-weight: normal;
        font-size: 14px;
        line-height: 28px;
        /* or 200% */
        letter-spacing: 0.003em;
        color: #828282;
      }

      &__img-slash {
        width: 750px;
        margin-top: 1.7rem;
      }
    }
  }

  //PREVIEW
  .preview {
    padding: 0;
    &__card {
      width: 320px;
      margin: 0;

      &-img {
        width: 100%;
      }

      &-title {
        // display: block;
        // flex-direction: row;
        // flex-wrap: wrap;
        // align-content: flex-start;
        padding-left: 0;
        padding-right: 0;
        padding-top: 1.5rem;
        h3 {
          font-weight: 600;
          font-size: 16px;
          line-height: 24px;
          /* identical to box height, or 150% */

          letter-spacing: 0.003em;

          /* font */

          color: #1e1b1b;
        }
      }

      .technology {
        &__img {
          padding-right: 16px;
        }
      }

      &-action {
        margin-top: 1rem;
        padding: 0;
      }
    }
  }

  //ADVERTISEMENT
  .advertisement {
    margin-top: 1rem;
    padding: 0rem;
    &__hero {
      padding: 1rem;
      // margin-top: 3.8rem;

      h1 {
        // margin-top: 1rem;
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 24px;
        line-height: 35px;
        /* or 146% */
        /* FONT COLOUR */
        color: #2e186a;
      }

      p {
        font-style: normal;
        font-weight: normal;
        font-size: 14px;
        line-height: 28px;
        /* or 200% */

        letter-spacing: 0.003em;

        color: #545f8d;
      }
    }
  }

  //COLLABORATION
  .colab {
    &__left {
      padding: 0;
    }

    margin-top: 2rem;
    padding: 1rem;
    &__title {
      h1 {
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 24px;
        line-height: 35px;
        /* or 146% */
        /* FONT COLOUR */
        color: #2e186a;
      }

      p {
        font-style: normal;
        font-weight: normal;
        font-size: 16px;
        line-height: 28px;
        /* or 175% */
        letter-spacing: 0.003em;
        color: #828282;
      }
    }

    &__img-hero {
      margin-top: 3rem;
      margin-bottom: 4rem;

      img {
        height: 500px;
      }
    }
  }

  //TECHNOLOGY WE USED
  .ourtech {
    padding-bottom: 5rem;
    &__title {
      h1 {
        padding-top: 3rem;
        padding-bottom: 2rem;
        font-style: normal;
        font-weight: bold;
        font-size: 24px;
        line-height: 40px;
        /* or 167% */
        text-align: center;
        letter-spacing: 0.003em;

        /* FONT COLOUR */

        color: #2e186a;
      }
    }
    &__item {
      padding: 0;
    }

    &__img-wrap {
      img {
        width: 65px;
      }
    }
  }

  //FOOTER
  .footer {
    &__card {
      background-image: url('@/assets/images/Footer.svg');
      background-color: #f0f3ff;

      &-title {
        padding-top: 5rem;
        padding-left: 0rem;
        padding: 0 1.2rem;
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 18px;
        line-height: 35px;
        /* or 140% */

        letter-spacing: 0.003em;

        color: #ffffff;
      }
    }

    &__btn {
      margin-top: 2rem;
    }
  }
}

@media screen and (min-width: 600px) and (max-width: 960px) {
  // shadow navbar mobile
  .v-sheet.v-app-bar.v-toolbar:not(.v-sheet--outlined) {
    box-shadow: 0px 2px 4px -1px rgb(0 0 0 / 0%),
      0px 4px 5px 0px rgb(0 0 0 / 10%), 0px 14px 4px rgb(0 0 0 / 2%);
  }

  .hero {
    margin-top: 5rem;

    &__text {
      margin-left: 0;
      padding: 28px;
      margin-left: 2.5rem;
      margin-right: 2.5rem;

      h1 {
        color: #2e186a;
        font-family: $font-inter;
        font-weight: 700;
        font-size: 52px;
        line-height: 70px;
        margin-bottom: 1.5rem;
      }

      h4 {
        font-style: normal;
        font-weight: 400;
        font-size: 17px;
        line-height: 25px;
      }
    }
    .btn {
      margin-top: 2rem;
    }

    &__btn {
      height: 43px;
      background: linear-gradient(94.5deg, #fe8d0d -7.68%, #eeb00f 109.25%);
      font-size: 11px;
    }

    .illu__hero {
      position: relative;
      float: right;
      height: 475px;

      img {
        position: absolute;
        width: calc(100vh - 360px);
        top: -107px;
        right: 0;
      }
    }
  }

  // SERVICES
  .services {
    padding: 28px;
    margin: 0 2.5rem;
    &__wrap {
      // padding: 1rem;
      margin-left: 0;
      margin-top: 0rem;
    }

    &__hero {
      // &-div {
      //   margin-left: 3.5rem;
      // }

      // text-align: center;
      padding: 0;
      margin-top: 1rem;
      margin-bottom: 2rem;
      h2 {
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 28px;
        line-height: 35px;
        /* or 146% */
        letter-spacing: 0.003em;
        /* FONT COLOUR */
        color: #2e186a;
      }

      span {
        font-style: normal;
        font-weight: normal;
        font-size: 14px;
        line-height: 28px;
        /* or 200% */
        letter-spacing: 0.003em;
        color: #828282;
      }
    }

    &__card {
      // margin: 10px;
      padding: 16px;
      &-title {
        padding: 5px;
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 18px;
        line-height: 22px;
        /* identical to box height, or 122% */
        text-align: center;
        letter-spacing: 0.003em;
      }

      &-subtitle {
        padding: 5px;
        font-family: $font-inter;
        font-style: normal;
        font-weight: normal;
        font-size: 13px;
        line-height: 18px;
        /* or 138% */
        text-align: left;
        letter-spacing: 0.003em;

        color: #828282;
      }
    }
  }

  //PROJECTS
  .projects {
    margin-top: 0rem;
    padding: 28px;
    margin: 0 2.5rem;

    &__img {
      width: 10vh;
    }

    &__hero {
      h1 {
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 24px;
        line-height: 35px;
        /* or 146% */
        letter-spacing: 0.003em;
        /* FONT COLOUR */
        color: #2e186a;
      }

      p {
        margin-top: 1rem;
        font-style: normal;
        font-weight: normal;
        font-size: 14px;
        line-height: 28px;
        /* or 200% */
        letter-spacing: 0.003em;
        color: #828282;
      }
    }
    &__img-slash {
      width: 450px;
      margin-top: 1.7rem;
      margin: 0 auto;
    }
  }

  //PREVIEW
  .preview {
    padding: 0;
    &__card {
      width: 450px;
      margin: 0;

      &-img {
        width: 100%;
      }

      &-title {
        // display: block;
        // flex-direction: row;
        // flex-wrap: wrap;
        // align-content: flex-start;
        padding-left: 0;
        padding-right: 0;
        padding-top: 1.5rem;
        h3 {
          font-weight: 600;
          font-size: 16px;
          line-height: 24px;
          /* identical to box height, or 150% */

          letter-spacing: 0.003em;

          /* font */

          color: #1e1b1b;
        }
      }

      .technology {
        &__img {
          padding-right: 16px;
        }
      }

      &-action {
        margin-top: 1rem;
        padding: 0;
      }
    }
  }

  //ADVERTISEMENT
  .advertisement {
    &__img {
      width: 500px;
      margin: 5px auto;
    }

    margin-top: 1rem;
    padding: 0rem;
    &__hero {
      padding: 28px;
      margin: 0 2.5rem;

      // margin-top: 3.8rem;

      h1 {
        // margin-top: 1rem;
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 24px;
        line-height: 35px;
        /* or 146% */
        /* FONT COLOUR */
        color: #2e186a;
      }

      p {
        font-style: normal;
        font-weight: normal;
        font-size: 14px;
        line-height: 28px;
        /* or 200% */

        letter-spacing: 0.003em;

        color: #545f8d;
      }
    }
  }

  //COLLABORATION
  .colab {
    margin-top: 2rem;
    margin-left: 2.5rem;
    margin-right: 2.5rem;
    padding: 1rem;
    &__title {
      h1 {
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 24px;
        line-height: 35px;
        /* or 146% */
        /* FONT COLOUR */
        color: #2e186a;
      }

      p {
        font-style: normal;
        font-weight: normal;
        font-size: 16px;
        line-height: 28px;
        /* or 175% */
        letter-spacing: 0.003em;
        color: #828282;
      }
    }

    &__img-hero {
      margin-top: 3rem;
      margin-bottom: 4rem;

      img {
        height: 500px;
      }
    }
  }

  //TECHNOLOGY WE USED
  .ourtech {
    padding-bottom: 5rem;
    &__title {
      h1 {
        padding-top: 3rem;
        padding-bottom: 2rem;
        font-style: normal;
        font-weight: bold;
        font-size: 24px;
        line-height: 40px;
        /* or 167% */
        text-align: center;
        letter-spacing: 0.003em;

        /* FONT COLOUR */

        color: #2e186a;
      }
    }
    &__item {
      padding: 0;
    }

    &__img-wrap {
      img {
        width: 65px;
      }
    }
  }

  //FOOTER
  .footer {
    padding: 28px;

    &__card {
      background-image: url('@/assets/images/Footer.svg');
      background-color: #f0f3ff;

      &-title {
        margin: 0 2.5rem;
        padding-top: 5rem;
        padding-left: 0rem;
        padding: 0 1.2rem;
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 18px;
        line-height: 35px;
        /* or 140% */

        letter-spacing: 0.003em;

        color: #ffffff;
      }
    }

    &__btn {
      margin-top: 2rem;
    }
  }
}

@media screen and (min-width: 960px) and (max-width: 1264px) {
  .hero {
    margin-top: 5rem;

    .v-btn:not(.v-btn--round).v-size--default {
      height: 45px;
      font-size: 14px;
      background: linear-gradient(94.5deg, #fe8d0d -7.68%, #eeb00f 109.25%);
    }

    &__text {
      margin-left: 0;
      padding: 16px;
      margin-left: 2.5rem;
      margin-right: 2.5rem;

      h1 {
        color: #2e186a;
        font-family: $font-inter;
        font-style: normal;
        font-weight: bold;
        font-size: 73px;
        line-height: 100px;
        margin-bottom: 1rem;
      }

      h4 {
        font-style: normal;
        font-weight: 400;
        font-size: 18px;
        line-height: 25px;
      }
    }
    .btn {
      margin-top: 2rem;
    }

    .illu__hero {
      position: relative;
      float: right;
      height: 550px;

      img {
        position: absolute;
        width: calc(100vh - 150px);
        top: 0;
        right: 0;
      }
    }
  }

  // SERVICES
  .services {
    padding: 16px;
    margin: 0 2.5rem;
    &__wrap {
      margin-left: 0;
      margin-top: 0rem;
    }

    &__hero {
      &-div {
        margin-top: 2rem;
      }

      padding: 0;
      margin-top: 1rem;
      margin-bottom: 2rem;
      h2 {
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 28px;
        line-height: 35px;
        /* or 146% */
        letter-spacing: 0.003em;
        /* FONT COLOUR */
        color: #2e186a;
      }

      span {
        font-style: normal;
        font-weight: normal;
        font-size: 14px;
        line-height: 28px;
        /* or 200% */
        letter-spacing: 0.003em;
        color: #828282;
      }
    }

    &__card {
      margin-left: 1rem;
      // margin: 10px;
      padding: 8px;
      &-title {
        padding: 5px;
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 18px;
        line-height: 22px;
        /* identical to box height, or 122% */
        text-align: center;
        letter-spacing: 0.003em;
      }

      img {
        width: 30px;
      }

      &-subtitle {
        padding: 5px;
        font-family: $font-inter;
        font-style: normal;
        font-weight: normal;
        font-size: 13px;
        line-height: 18px;
        /* or 138% */
        text-align: left;
        letter-spacing: 0.003em;

        color: #828282;
      }
    }
  }

  //PROJECTS
  .projects {
    margin-top: 0rem;
    padding: 16px;
    margin: 0 2.5rem;

    &__img {
      width: 10vh;
    }

    &__hero {
      h1 {
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 28px;
        line-height: 35px;
        /* or 146% */
        letter-spacing: 0.003em;
        /* FONT COLOUR */
        color: #2e186a;
      }

      p {
        margin-top: 1rem;
        font-style: normal;
        font-weight: normal;
        font-size: 14px;
        line-height: 28px;
        /* or 200% */
        letter-spacing: 0.003em;
        color: #828282;
      }
    }
    &__img-slash {
      width: 450px;
      margin-top: 1.7rem;
      margin: 0 auto;
    }
  }

  //PREVIEW
  .preview {
    padding: 0;
    &__card {
      width: 450px;
      margin: 1.5rem;

      &-img {
        width: 100%;
      }

      &-title {
        // display: block;
        // flex-direction: row;
        // flex-wrap: wrap;
        // align-content: flex-start;
        padding-left: 0;
        padding-right: 0;
        padding-top: 1.5rem;
        h3 {
          font-weight: 600;
          font-size: 16px;
          line-height: 24px;
          /* identical to box height, or 150% */

          letter-spacing: 0.003em;

          /* font */

          color: #1e1b1b;
        }
      }

      .technology {
        &__img {
          padding-right: 16px;
        }
      }

      &-action {
        margin-top: 1rem;
        padding: 0;
      }
    }
  }

  //ADVERTISEMENT
  .advertisement {
    &__img {
      width: 500px;
      margin: 5px auto;
    }

    margin-top: 1rem;
    padding: 0rem;
    &__hero {
      padding: 16px;
      margin: 0 2.5rem;

      // margin-top: 3.8rem;

      h1 {
        // margin-top: 1rem;
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 28px;
        line-height: 35px;
        /* or 146% */
        /* FONT COLOUR */
        color: #2e186a;
      }

      p {
        font-style: normal;
        font-weight: normal;
        font-size: 14px;
        line-height: 28px;
        /* or 200% */

        letter-spacing: 0.003em;

        color: #545f8d;
      }
    }
  }

  //COLLABORATION
  .colab {
    margin-top: 2rem;
    margin-left: 2.5rem;
    margin-right: 2.5rem;
    padding: 1rem;
    &__title {
      h1 {
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 28px;
        line-height: 35px;
        /* or 146% */
        /* FONT COLOUR */
        color: #2e186a;
      }

      p {
        font-style: normal;
        font-weight: normal;
        font-size: 16px;
        line-height: 28px;
        /* or 175% */
        letter-spacing: 0.003em;
        color: #828282;
      }
    }

    &__img-hero {
      margin-top: 3rem;
      margin-bottom: 4rem;

      img {
        height: 500px;
      }
    }
  }

  //TECHNOLOGY WE USED
  .ourtech {
    padding-bottom: 5rem;
    &__title {
      h1 {
        padding-top: 3rem;
        padding-bottom: 2rem;
        font-style: normal;
        font-weight: bold;
        font-size: 28px;
        line-height: 40px;
        /* or 167% */
        text-align: center;
        letter-spacing: 0.003em;

        /* FONT COLOUR */

        color: #2e186a;
      }
    }
    &__item {
      padding: 2rem 15rem;
    }

    &__img-wrap {
      margin: 2rem;
      img {
        width: 65px;
      }
    }
  }

  //FOOTER
  .footer {
    padding: 16px;

    &__card {
      background-image: url('@/assets/images/Footer.svg');
      background-color: #f0f3ff;

      &-title {
        margin: 0 2.5rem;
        padding-top: 5rem;
        padding-left: 0rem;
        padding: 0 1.2rem;
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 18px;
        line-height: 35px;
        /* or 140% */

        letter-spacing: 0.003em;

        color: #ffffff;
      }
    }

    &__btn {
      margin-top: 3rem;
    }
  }
}

@media screen and (min-width: 1264px) and (max-width: 1904px) {
  // padding left & right navbar
  .nav__pa-left,
  .nav__pa-right {
    padding: 0 3rem;
  }

  .hero {
    margin-top: 7rem;

    .v-btn:not(.v-btn--round).v-size--default {
      height: 55px;
      font-size: 14px;
      background: linear-gradient(94.5deg, #fe8d0d -7.68%, #eeb00f 109.25%);
    }

    &__text {
      margin-left: 3rem;

      h1 {
        color: #2e186a;
        font-family: $font-inter;
        font-weight: bolder;
        font-size: 88px;
        line-height: 110px;
        margin-bottom: 3rem;
      }

      h4 {
        font-style: normal;
        font-weight: normal;
        font-size: 18px;
        color: #2e186a;
        line-height: 14px;
      }
    }
    .btn {
      margin-top: 3rem;
    }

    .illu__hero {
      position: relative;
      float: right;
      height: 675px;

      img {
        position: absolute;
        width: calc(100vh - 50px);
        top: 0;
        right: 0;
      }
    }

    .illu__books {
      display: none;
      margin-top: 2rem;
      padding: 0;
    }
  }

  // SERVICES
  .services {
    padding: 0 3rem;
    &__wrap {
      padding: 1rem 0;
      margin-left: 6rem;
      margin-top: 8rem;
    }

    &__hero {
      margin-top: 2rem;
      h2 {
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 30px;
        line-height: 50px;
        /* or 128% */

        letter-spacing: 0.003em;

        /* FONT COLOUR */
        color: #2e186a;
        margin-bottom: 1rem;
      }

      span {
        font-style: normal;
        font-weight: normal;
        font-size: 16px;
        line-height: 30px;
        /* or 167% */

        letter-spacing: 0.003em;

        color: #828282;
      }
    }

    &__card {
      margin: 10px;
      padding: 6px;
      &-title {
        padding: 5px;
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 18px;
        line-height: 22px;
        /* identical to box height, or 122% */
        text-align: center;
        letter-spacing: 0.003em;
      }

      &-subtitle {
        padding: 5px;
        font-family: $font-inter;
        font-style: normal;
        font-weight: normal;
        font-size: 13px;
        line-height: 18px;
        /* or 138% */
        text-align: left;
        letter-spacing: 0.003em;

        color: #828282;
      }
    }
  }

  //PROJECTS
  .projects {
    margin-top: 4rem;
    &__hero {
      text-align: left;
      h1 {
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 30px;
        line-height: 25px;
        /* identical to box height, or 64% */
        letter-spacing: 0.003em;
        /* FONT COLOUR */
        color: #2e186a;
      }

      p {
        margin-top: 2rem;
        font-style: normal;
        font-weight: normal;
        font-size: 18px;
        line-height: 24px;
        /* identical to box height, or 133% */
        letter-spacing: 0.003em;

        color: #828282;
      }
    }
    &__img-slash {
      margin: 0 auto;
      width: 500px;
      margin-top: 1.7rem;
    }
  }

  //PREVIEW
  .preview {
    &__card {
      // margin: 20px;
      padding: 0 2rem;
      &-title {
        padding-left: 8px;
        padding-right: 0;
        padding-top: 1.5rem;
        h3 {
          font-style: normal;
          font-weight: 600;
          font-size: 18px;
          line-height: 24px;
          /* identical to box height, or 133% */

          letter-spacing: 0.003em;

          /* font */
          color: #1e1b1b;
        }
      }
      .technology {
        margin: 1rem;
        &__img {
          width: 55px;
        }
      }

      &-action {
        padding: 0;
      }
    }
  }

  //ADVERTISEMENT
  .advertisement {
    margin-top: 1rem;
    padding-top: 4rem;
    &__hero {
      // margin-top: 3.8rem;

      h1 {
        // margin-top: 1rem;
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 39px;
        line-height: 50px;
        /* or 128% */
        /* FONT COLOUR */
        color: #2e186a;
      }

      p {
        margin-top: 1.5rem;
        font-style: normal;
        font-weight: normal;
        font-size: 18px;
        line-height: 30px;
        /* or 167% */
        letter-spacing: 0.003em;
        color: #545f8d;
      }
    }
  }

  //COLLABORATION
  .colab {
    margin-top: 1rem;
    padding: 5rem;
    &__title {
      h1 {
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 39px;
        line-height: 50px;
        margin-bottom: 1.5rem;
        /* or 128% */
        /* FONT COLOUR */
        color: #2e186a;
      }

      p {
        font-weight: normal;
        font-size: 18px;
        line-height: 30px;

        /* or 167% */
        letter-spacing: 0.003em;

        color: #828282;
      }
    }

    &__img-hero {
      margin-top: 5rem;
      margin-bottom: 4rem;
    }
  }

  //TECHNOLOGY WE USED
  .ourtech {
    padding-bottom: 10rem;
    &__title {
      h1 {
        padding-top: 6rem;
        padding-bottom: 3rem;
        font-family: $font-inter;
        font-style: normal;
        font-weight: bold;
        font-size: 39px;
        line-height: 60px;
        /* or 154% */

        text-align: center;
        letter-spacing: 0.003em;

        /* FONT COLOUR */

        color: #2e186a;
      }
    }
    &__item {
      padding: 1rem 15rem;
    }

    &__img-wrap {
      margin: 1.5rem;
      img {
        width: 75px;
      }
    }
  }

  //FOOTER
  .footer {
    &__card {
      background-image: url('@/assets/images/Footer.svg');
      background-color: #f0f3ff;

      &-title {
        margin: 0 2.5rem;
        padding: 5rem 1.2rem 0 1.2rem;
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 24px;
        line-height: 50px;
        /* or 128% */

        letter-spacing: 0.003em;

        color: #ffffff;
      }
    }

    &__btn {
      margin-top: 3rem;
    }
  }
}

@media screen and (min-width: 1904px) {
  // padding left & right navbar
  .nav__pa-left,
  .nav__pa-right {
    padding: 0 8rem;
  }

  .hero {
    .hero__btn {
      font-size: 1rem;
    }

    margin-top: 7rem;

    .v-btn:not(.v-btn--round).v-size--default {
      height: 55px;
      font-size: 14px;
      background: linear-gradient(94.5deg, #fe8d0d -7.68%, #eeb00f 109.25%);
    }

    &__text {
      margin-left: 8rem;

      h1 {
        color: #2e186a;
        font-family: $font-inter;
        font-weight: bold;
        font-size: 96px;
        line-height: 130px;
        margin-bottom: 3rem;
      }

      h4 {
        font-style: normal;
        font-weight: normal;
        font-size: 22px;
        color: #2e186a;
        line-height: 14px;
      }
    }
    .btn {
      margin-top: 3rem;
    }

    .illu__hero {
      position: relative;
      float: right;
      height: 850px;

      img {
        position: absolute;
        width: 100vh;
        top: 0;
        right: 0;
      }
    }

    .illu__books {
      display: flex;
      position: relative;
      // margin-top: 4rem;
      padding: 0;

      img {
        position: absolute;
        left: 0;
        width: 200px;
        top: 50px;
      }
    }
  }

  // SERVICES
  .services {
    padding: 0 8rem;
    &__wrap {
      padding: 1rem 0;
      margin-left: 6rem;
      margin-top: 8rem;
    }

    &__hero {
      margin-top: 2rem;
      h2 {
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 40px;
        line-height: 50px;
        /* or 128% */

        letter-spacing: 0.003em;

        /* FONT COLOUR */
        color: #2e186a;
        margin-bottom: 1rem;
      }

      span {
        font-style: normal;
        font-weight: normal;
        font-size: 18px;
        line-height: 30px;
        /* or 167% */

        letter-spacing: 0.003em;

        color: #828282;
      }
    }

    &__card {
      width: 360px;
      height: 130px;
      margin: 1rem;
      padding: 1rem;
      &-title {
        padding: 5px;
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 20px;
        line-height: 22px;
        /* identical to box height, or 122% */
        text-align: center;
        letter-spacing: 0.003em;
      }

      &-subtitle {
        padding: 5px;
        font-family: $font-inter;
        font-style: normal;
        font-weight: normal;
        font-size: 16px;
        line-height: 22px;
        /* or 138% */
        text-align: left;
        letter-spacing: 0.003em;

        color: #828282;
      }
    }
  }

  //PROJECTS
  .projects {
    margin-top: 6rem;
    &__hero {
      text-align: left;
      h1 {
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 40px;
        line-height: 25px;
        /* identical to box height, or 64% */
        letter-spacing: 0.003em;
        /* FONT COLOUR */
        color: #2e186a;
      }

      p {
        margin-top: 2rem;
        font-style: normal;
        font-weight: normal;
        font-size: 18px;
        line-height: 24px;
        /* identical to box height, or 133% */
        letter-spacing: 0.003em;

        color: #828282;
      }
    }
    &__img-slash {
      margin: 0 auto;
      width: 500px;
      margin-top: 1.7rem;
    }
  }

  //PREVIEW
  .preview {
    &__card {
      width: 756px;
      // margin: 20px;
      padding: 0rem;
      margin: 2rem;
      &-title {
        padding-left: 8px;
        padding-right: 0;
        padding-top: 1.5rem;
        h3 {
          font-style: normal;
          font-weight: 600;
          font-size: 18px;
          line-height: 24px;
          /* identical to box height, or 133% */

          letter-spacing: 0.003em;

          /* font */
          color: #1e1b1b;
        }
      }
      .technology {
        margin: 1rem;
        &__img {
          width: 100%;
        }
      }

      &-action {
        padding: 0;
      }
    }
  }

  //ADVERTISEMENT
  .advertisement {
    margin-top: 1rem;
    padding-top: 4rem;

    &__hero {
      // margin-top: 3.8rem;
      padding-left: 8rem;

      h1 {
        // margin-top: 1rem;
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 40px;
        line-height: 50px;
        /* or 128% */
        /* FONT COLOUR */
        color: #2e186a;
      }

      p {
        margin-top: 1.5rem;
        font-style: normal;
        font-weight: normal;
        font-size: 18px;
        line-height: 30px;
        /* or 167% */
        letter-spacing: 0.003em;
        color: #545f8d;
      }
    }
  }

  //COLLABORATION
  .colab {
    margin-top: 1rem;
    padding: 8rem;
    &__title {
      h1 {
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 40px;
        line-height: 50px;
        margin-bottom: 1.5rem;
        /* or 128% */
        /* FONT COLOUR */
        color: #2e186a;
      }

      p {
        font-weight: normal;
        font-size: 18px;
        line-height: 30px;

        /* or 167% */
        letter-spacing: 0.003em;
        color: #828282;
      }
    }

    &__img-hero {
      margin-top: 8rem;
      margin-bottom: 5rem;
    }
  }

  //TECHNOLOGY WE USED
  .ourtech {
    padding-bottom: 10rem;
    &__title {
      h1 {
        padding-top: 6rem;
        padding-bottom: 3rem;
        font-family: $font-inter;
        font-style: normal;
        font-weight: bold;
        font-size: 39px;
        line-height: 60px;
        /* or 154% */

        text-align: center;
        letter-spacing: 0.003em;

        /* FONT COLOUR */

        color: #2e186a;
      }
    }
    &__item {
      padding: 1rem 30rem;
    }

    &__img-wrap {
      margin: 2rem;
      img {
        width: 75px;
      }
    }
  }

  //FOOTER
  .footer {
    &__card {
      background-image: url('@/assets/images/Footer.svg');
      background-color: #f0f3ff;

      &-title {
        margin: 0 2.5rem;
        padding: 5rem 1.2rem 0 1.2rem;
        font-family: $font-inter;
        font-style: normal;
        font-weight: 600;
        font-size: 24px;
        line-height: 50px;
        /* or 128% */

        letter-spacing: 0.003em;

        color: #ffffff;
      }
    }

    &__btn {
      margin-top: 3rem;
    }
  }
}
</style>
