<template>
  <v-card class="overflow-hidden">
    <v-app-bar
      absolute
      color="white"
      elevate-on-scroll
      scroll-target="#scrolling-techniques-7"
    >
      <v-toolbar-title class="nav__pa-left"
            ><v-img :src="require('@/assets/images/logo.png')"></v-img>
          </v-toolbar-title>

          <v-spacer></v-spacer>
          <div class="d-flex justify-center align-center nav__pa-right">
            <ul>
              <li><NuxtLink class="navbar__item" to="/">Work</a></NuxtLink></li>
              <li><NuxtLink class="navbar__item" to="/about">About</a></NuxtLink></li>
              <li><NuxtLink class="navbar__item" to="/contact">Contact</a></NuxtLink></li>
            </ul>
          </div>
    </v-app-bar>
    <v-sheet
      id="scrolling-techniques-7"
      class="overflow-y-auto"
      max-height="100vh"
    >
      <v-container fluid style=" margin-top:8rem">
        <!-- SECTION 1 - HERO -->
        <section class="hero">
          <v-row>
            <v-col cols="8">
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

            <v-row>
              <v-col cols="12" class="pa-0" style="margin-top:5rem">
                <div style="position:relative; ">
                <v-img width="20vh":src="require('@/assets/images/buku.png')">
                </v-img>
              </div>
            </v-col>
            </v-row>

            </v-col>
            
            <v-col cols="4" class="pa-0">
              <div style="position:relative;">
                <img style="position:absolute; right:0; top:10%;" :src="require('@/assets/images/hero_img.png')" >
                </v-img>
              </div>
            </v-col>
          </v-row>
        </section>

        <section class="services">
          <v-row class="services__wrap">
            <v-col cols="5"  class="services__hero">
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
               <v-hover v-slot="{ hover }">
                <v-card width="320px" class="services__card rounded-lg" :style="
                        hover
                          ? 'box-shadow: 2px 7px 26px rgba(0, 0, 0, 0.10);'
                          : 'box-shadow: 2px 7px 26px rgba(0, 0, 0, 0.06);'
                      ">
                    <v-card-title class="services__card-title"> 
                      <img class="mr-2"  :src="require('@/assets/images/icon-card/1.png')" alt="icon-grow-your-bussiness"> 
                      Grow Your Bussiness
                    </v-card-title>
                      <div class="services__card-subtitle">
                        grow your business by creating the perfect website
                      </div>
                </v-card>
               </v-hover>
               <v-hover v-slot="{ hover }">
                <v-card width="320px" class="services__card rounded-lg" :style="
                        hover
                          ? 'box-shadow: 2px 7px 26px rgba(0, 0, 0, 0.10);'
                          : 'box-shadow: 2px 7px 26px rgba(0, 0, 0, 0.06);'
                      ">
                    <v-card-title class="services__card-title"> 
                      <img class="mr-2"  :src="require('@/assets/images/icon-card/2.png')" alt="icon-grow-your-bussiness"> 
                      Bussiness Real Time Report
                    </v-card-title>
                      <div class="services__card-subtitle">
                        serve the making of your report program in real time
                      </div>
                </v-card>
               </v-hover>
               <v-hover v-slot="{ hover }">
                <v-card width="320px" class="services__card rounded-lg" :style="
                        hover
                          ? 'box-shadow: 2px 7px 26px rgba(0, 0, 0, 0.10);'
                          : 'box-shadow: 2px 7px 26px rgba(0, 0, 0, 0.06);'
                      ">
                    <v-card-title class="services__card-title"> 
                      <img class="mr-2"  :src="require('@/assets/images/icon-card/3.png')" alt="icon-grow-your-bussiness"> 
                      Automate your business
                    </v-card-title>
                      <div class="services__card-subtitle">
                        Serving automation to develop your project
                      </div>
                </v-card>
               </v-hover>
               <v-hover v-slot="{ hover }">
                <v-card width="320px" class="services__card rounded-lg" :style="
                        hover
                          ? 'box-shadow: 2px 7px 26px rgba(0, 0, 0, 0.10);'
                          : 'box-shadow: 2px 7px 26px rgba(0, 0, 0, 0.06);'
                      ">
                    <v-card-title class="services__card-title"> 
                      <img class="mr-2"  :src="require('@/assets/images/icon-card/4.png')" alt="icon-grow-your-bussiness"> 
                      Update your website
                    </v-card-title>
                      <div class="services__card-subtitle">
                        Our job is to help you develop a better website
                      </div>
                </v-card>
               </v-hover>
              </div>
              
            </v-col>
          </v-row>
        </section>
      </v-container>
    </v-sheet>
  </v-card>
</template>

<style lang="scss">
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
/* exact link will show the primary color for only the exact matching link */
a.nuxt-link-exact-active {
  font-weight: 600;
  // color: #f37272 !important;
  // border-bottom: 3px solid #FE7624;
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
    margin:10px;
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

.btn {
  margin-top: 3rem;
}
</style>
