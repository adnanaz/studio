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

        <v-app-bar-nav-icon class="mr-0" 
          ><img :src="require('@/assets/images/bar-chart.png')" alt="btn-toggle-navbar"
        /></v-app-bar-nav-icon>
      </div>
      
      <div :class="$vuetify.breakpoint.mdAndDown ? 'd-none' : 'd-flex'">
      <v-toolbar-title class="nav__pa-left"
            ><v-img :src="require('@/assets/images/logo.png')"></v-img>
      </v-toolbar-title>

          <v-spacer></v-spacer>
      <div class=" d-flex justify-center align-center nav__pa-right">
        <ul class="d-none">
          <li><NuxtLink class="navbar__item" to="/">Work</NuxtLink></li>
          <li><NuxtLink class="navbar__item" to="/about">About</NuxtLink></li>
          <li><NuxtLink class="navbar__item" to="/contact">Contact</NuxtLink></li>
        </ul>
      </div>
      </div>
      
    </v-app-bar>
    <!-- CONTENT -->
    <v-sheet
      id="scrolling-techniques-7"
      class="overflow-y-auto"
      max-height="100vh"
    >
        <!-- SECTION 1 - HERO -->
        <section class="hero">
          <v-row>
            <v-col cols="12" xs="12" sm="8" md="8" lg="8" xl="8">
              <div data-aos="fade-up"
              data-aos-offset="200"
              data-aos-delay="50"
              data-aos-duration="1500"
              data-aos-anchor-placement="top-center">
              <div class="hero__text">
              <h1>Developing your Website is Our Solution.</h1>

              <h4>Working with our team can develop your website even better</h4>
              <div class="btn">
                <v-hover  v-slot="{ hover }">
                <v-btn width="150"  elevation="0"  :style="
                      hover
                        ? 'box-shadow: rgba(0, 0, 0, 0.20) 0px 4px 12px !important'
                        : ''
                    " style="height:50px; background: linear-gradient(94.5deg, #FE8D0D -7.68%, #EEB00F 109.25%); " rounded class="white--text font-weight-regular text-capitalize" >
                  Lets Talk
                  <v-icon class="white--text" right>mdi-arrow-right</v-icon>
                </v-btn>
                </v-hover>
              </div>
            </div>
              </div>

            <v-row>
              <v-col cols="12" class="pa-0" style="margin-top:5rem">
                <div style="position:relative;">
                <v-img width="20vh":src="require('@/assets/images/buku.png')">
                </v-img>
              </div>
            </v-col>
            </v-row>
            </v-col>
            
            <v-col cols="12" xs="12" sm="4" md="4" lg="4" xl="4" class="pa-0">
              <div style="position:relative;">
                <div data-aos="fade-down"
              data-aos-offset="200"
              data-aos-delay="50"
              data-aos-duration="1500"
              data-aos-anchor-placement="top-center">
                <img style="position:absolute; right:0; top:10%;" :src="require('@/assets/images/hero-move.svg')" >
                </div>
              </div>
            </v-col>
          </v-row>
        </section>
        <!-- SECTION 2 - SERVICES -->
        <section class="services">
          <v-row class="services__wrap">
            <v-col cols="5" class="services__hero">
              <h2>
                The services we will <br>
                use to build your project
              </h2>
              <span>
                The result of trust from our customers who have <br>
                used the services of our team
              </span>
            </v-col>
            <v-col cols="7">
              <div class="d-flex justify-start align-center flex-wrap">
                <v-hover v-for="(el, idx) in card_services" :key="idx" v-slot="{ hover }">
                <v-card height="" width="320px" class="services__card rounded-lg" :style="
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
          <v-row >
            <!-- HERO -->
            <v-col cols="12">
              <div class="projects__wrap d-flex justify-center flex-wrap align-center">
                <div class="projects__hero">
                <h1>The work of our team, from several clients</h1>
                <p>The result of trust from our customers who have used the services of our team</p>
              </div>
              </div>
              <v-container>
              <v-img  style="width:750px; margin-top:1.7rem" :src="require('@/assets/images/project-slash.svg')"></v-img>
              </v-container>
            </v-col>
            <!-- PROJECT PREVIEW -->
            <v-col cols="12" class="preview">
              <v-container>
                
              <div class="d-flex justify-start flex-wrap" >
              <v-card  v-for="(el,index) in card_portofolio"
                elevation="0"
                :loading="loading"
                class="preview__card my-12"
                max-width="540"
                >
                <template slot="progress">
                  <v-progress-linear
                    color="deep-purple"
                    height="10"
                    indeterminate
                  ></v-progress-linear>
                </template>

                <v-img
                  height="368"
                  :src="require(`@/assets/images/portofolio/${el.img_url}`)"
                ></v-img>

                <v-card-title class="preview__card-title">
                  <h3>{{el.title}}</h3>

                  <v-spacer></v-spacer>

                <div class="technology d-flex justify-start align-center flex-wrap" v-for="(item, idx) in el.tech_img">
                  <v-img class="technology__img" :src="require(`@/assets/images/portofolio/tech/${item}.png`)"></v-img>
                </div>
              </v-card-title>

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
          <v-row>
            <v-col cols="5" class="pa-0">
              <v-img :src="require('@/assets/images/hero-2.svg')"></v-img>
            </v-col>
            <v-col cols="7" style="position:relative;" class="d-flex justify-start my-auto flex-column pa-0">
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
          <v-row>
            <v-col cols="6"  class="d-flex align-center colab__left">
              <div class="colab__title">
                <h1>
                  Collaboration between </br> our team
                </h1>
                <p>Our team believes that building a website is a cultural <br>
                relationship between companies and customers for 
                the better</p>
              </div>
            </v-col>
            <v-col cols="6" class="colab__right">
              <v-img class="colab__img" :src="require('@/assets/images/collaboration.svg')"></v-img>
            </v-col>
            
            <!-- GAMBAR BUILDING WEBSITE -->
            <v-col class="colab__img-hero" cols="12" align="center" justify="center">
              <v-img :src="require('@/assets/images/building-website.svg')"></v-img>
            </v-col>
          </v-row>
        </section>

        <!-- SECTION 6 - OUR TECHNOLOGY -->
        <section class="ourtech" style="background:#F0F3FF">
          <v-row>
            <v-col class="pa-0" cols="12">
              <div class="ourtech__title">
              <h1>
                  Our Technology in Developing <br> Your Website
              </h1>
              </div>
              <div class="d-flex justify-center flex-wrap align-center" style="padding:0 20rem;">
                  <div v-for="(el, idx) in technology_we_used" :key="idx" class="ourtech__img-wrap ma-7">
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
              <h1>When you need <br> project contact us</h1>
                 <div class="btn">
                <v-hover  v-slot="{ hover }">
                <v-btn width="150"  elevation="0"  :style="
                      hover
                        ? 'box-shadow: rgba(0, 0, 0, 0.20) 0px 4px 12px !important'
                        : ''
                    " style="height:50px; background: linear-gradient(94.5deg, #FE8D0D -7.68%, #EEB00F 109.25%); " rounded class="white--text font-weight-regular text-capitalize" >
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
  mounted() {},
}
</script>


<style lang="scss">
//shadow navbar mobile
// .v-sheet.v-app-bar.v-toolbar:not(.v-sheet--outlined) {
// box-shadow: 0px 2px 4px -1px rgb(0 0 0 / 0%), 0px 4px 5px 0px rgb(0 0 0 / 10%), 0px 14px 4px rgb(0 0 0 / 2%);
// }

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

/** 
STYLE
**/

// padding left & right navbar
.nav__pa-left,
.nav__pa-right {
  padding: 0 6rem;
}

.hero {
  margin-top: 10rem;
  &__text {
    margin-left: 6rem;

    h1 {
      color: #2e186a;
      font-family: $font-inter;
      font-weight: bolder;
      font-size: 96px;
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
}

.btn {
  margin-top: 3rem;
}

// SERVICES
.services {
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
      font-size: 39px;
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
    margin: 10px;
    padding: 5px;
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
      font-size: 39px;
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
}

//PREVIEW
.preview {
  &__card {
    margin: 20px;
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

      .technology {
        &__img {
          margin: 0 8px;
        }
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
      font-style: normal;
      font-weight: normal;
      font-size: 18px;
      line-height: 30px;
      /* or 167% */
      letter-spacing: 0.003em;
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
      padding-bottom: 4rem;
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
}

//FOOTER
.footer {
  &__card {
    background-image: url('@/assets/images/Footer.svg');
    background-color: #f0f3ff;

    &-title {
      padding-top: 5rem;
      padding-left: 5rem;
      font-family: $font-inter;
      font-style: normal;
      font-weight: 600;
      font-size: 28px;
      line-height: 50px;
      /* or 128% */

      letter-spacing: 0.003em;

      color: #ffffff;
    }
  }
}

// MEDIA QUERY
@media screen and (min-width: 300px) and (max-width: 600px) {
}

@media screen and (min-width: 600px) and (max-width: 960px) {
}
</style>
