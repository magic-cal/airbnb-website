<template>
  <v-content>
    <section id="hero">
      <v-row no-gutters>
        <v-img
          :min-height="'calc(100vh)'"
          :max-height="'calc(100vh)'"
          src="https://wheretogowithkids.co.uk/wp-content/uploads/2020/11/chapel-st-leonards-beach-chapel-point-1200x800-1-1024x683.jpg"
        >
          <v-theme-provider dark>
            <v-container fill-height fluid>
              <v-row
                align="center"
                class="white--text mx-auto"
                justify="center"
              >
                <v-col class="white--text text-center" cols="12" tag="h1">
                  <span
                    :class="[
                      $vuetify.breakpoint.smAndDown ? 'display-1' : 'display-2',
                    ]"
                    class="font-weight-light"
                  >
                    WELCOME TO
                  </span>
                  <br />
                  <span
                    :class="[
                      $vuetify.breakpoint.smAndDown ? 'display-3' : 'display-4',
                    ]"
                    class="font-weight-black"
                  >
                    The Seaside Retreat
                  </span>
                </v-col>

                <v-btn
                  class="align-self-end"
                  fab
                  outlined
                  @click="$vuetify.goTo('#about-me')"
                >
                  <v-icon>mdi-chevron-double-down</v-icon>
                </v-btn>
              </v-row>
            </v-container>
          </v-theme-provider>
        </v-img>
      </v-row>
    </section>

    <section id="about-me">
      <div class="py-12"></div>

      <v-container class="text-center">
        <h2 class="display-2 font-weight-bold mb-3">About</h2>
        <span class="display-1 grey--text text--darken-1 font-weight-bold">
          Great for family time, relaxing and dog walks.
        </span>

        <v-responsive class="mx-auto mb-8" width="56">
          <v-divider class="mb-1"></v-divider>

          <v-divider></v-divider>
        </v-responsive>

        <v-responsive
          class="mx-auto title font-weight-light mb-8"
          max-width="720"
        >
          A cosy, self-contained, holiday chalet 3 mins walk from endless,
          sandy, ‘bucket and spade’ beach. Simple, well-equipped accessible
          chalet on private site with fishing lake. Own private patio area. One
          double, one twin bedroom. Lovely kitchen and shower room. On site
          parking . TV and Internet available
        </v-responsive>

        <v-row justify="center" align="center">
          <v-col cols="6" sm="4">
            <v-img src="/living.png"></v-img>
          </v-col>

          <v-col cols="6" sm="4">
            <v-img src="/shower.jpg"> </v-img>
          </v-col>

          <v-col v-if="$vuetify.breakpoint.mdAndUp" cols="6" sm="4">
            <v-img src="/kitchen.jpg"> </v-img>
          </v-col>
        </v-row>

        <div></div>
      </v-container>

      <div class="py-12"></div>
    </section>

    <section id="features" class="grey lighten-3">
      <div class="py-12"></div>

      <v-container class="text-center">
        <h2 class="display-2 font-weight-bold mb-3">Locally</h2>
        <v-responsive class="mx-auto mb-8" width="56">
          <v-divider class="mb-1"></v-divider>

          <v-divider></v-divider>
        </v-responsive>

        <v-row class="mx-auto title font-weight-light mb-8">
          <v-col :cols="12" :sm="6">
            <div>Beautiful local towns</div>
            <div>Bus to Skegness - a complete contrast!</div>
            <div>
              3 minutes to the beach and North Coast Observatory with great
              healthy menu and fab coffee
            </div>
          </v-col>
          <v-col v-if="$vuetify.breakpoint.xsOnly">
            <v-divider></v-divider>
          </v-col>
          <v-col :cols="12" :sm="6">
            <div>Great takeaways delivered to the site</div>
            <div>Great Sunday roasts at local pub</div>
            <div>Private fishing lake</div>
            <div>
              <a href="https://www.eastfieldspark.co.uk/gallery">
                https://www.eastfieldspark.co.uk/gallery
              </a>
            </div>
          </v-col>
        </v-row>

        <v-row>
          <v-col
            v-for="({ icon, title, text }, i) in features"
            :key="i"
            cols="12"
            md="4"
          >
            <v-card class="py-12 px-4" color="grey lighten-5" flat>
              <v-theme-provider dark>
                <div>
                  <v-avatar color="primary" size="88">
                    <v-icon large v-text="icon"></v-icon>
                  </v-avatar>
                </div>
              </v-theme-provider>

              <v-card-title
                class="justify-center font-weight-black text-uppercase"
                v-text="title"
              ></v-card-title>

              <v-card-text class="subtitle-1" v-text="text"> </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>

      <div class="py-12"></div>
    </section>

    <section id="stats">
      <v-parallax
        :height="$vuetify.breakpoint.smAndDown ? 700 : 500"
        src="https://www.surf-forecast.com/system/images/14628/large/Chapel-St-Leonards.jpg?1442732213"
      >
        <v-container fill-height>
          <v-row class="mx-auto">
            <v-col cols="12" md="6">
              <div class="text-center">
                <div class="display-2 font-weight-black mb-4">
                  Price Per Month
                </div>

                <div class="title font-weight-regular text-uppercase">£400</div>
              </div>
            </v-col>
            <v-col cols="12" md="6">
              <div class="text-center">
                <div class="display-2 font-weight-black mb-4">
                  School Holidays
                </div>

                <div class="title font-weight-regular text-uppercase">£500</div>
              </div>
            </v-col>
          </v-row>
        </v-container>
      </v-parallax>
    </section>

    <section id="blog">
      <div class="py-12"></div>

      <v-container>
        <h2 class="display-1 font-weight-bold mb-3 text-uppercase text-center">
          Why so cheap?
        </h2>

        <v-responsive class="mx-auto mb-12" width="56">
          <v-divider class="mb-1"></v-divider>

          <v-divider></v-divider>
        </v-responsive>

        <v-row>
          <v-col cols="12" md="4" class="text-center">
            It is close to Skegness - but not too close- a little piece of
            heaven It is a simple space but not so much storage so pack light.
          </v-col>
          <v-col cols="12" md="4" class="text-center">
            It is in an undiscovered part of the East Lincolnshire coast so
            prices are still well within reach.
          </v-col>
          <v-col cols="12" md="4" class="text-center">
            The inside is just lovely, the outside simple and functional - it is
            not The Ritz but we think you will love it - we certainly do!</v-col
          >
        </v-row>
      </v-container>

      <div class="py-12"></div>
    </section>

    <v-sheet id="contact" color="#333333" dark tag="section" tile>
      <div class="py-12"></div>

      <v-container>
        <h2 class="display-2 font-weight-bold mb-3 text-uppercase text-center">
          Contact Us
        </h2>

        <v-responsive class="mx-auto mb-12" width="56">
          <v-divider class="mb-1"></v-divider>

          <v-divider></v-divider>
        </v-responsive>

        <v-row>
          <v-col :cols="12" :sm="6">
            <h2 class="display-1 font-weight-bold mb-3 text-uppercase">
              Do call, we are happy to answer any questions
            </h2>

            <div>
              <div class="font-weight-bold mb-3 title">Chris and Ali</div>

              <a
                class="font-weight-bold mb-3 title white--text"
                href="tel:07816 408181"
                >07816 408181</a
              >
              <br />
              <a
                class="font-weight-bold mb-3 title white--text"
                href="mailto:callum.mcclure98@gmail.com"
                >alimcclure@hotmail.com</a
              >
            </div>
          </v-col>

          <v-col :cols="12" :sm="6">
            <v-theme-provider light>
              <form
                action="mailto:callum.mcclure98@gmail.com"
                method="POST"
                enctype="text/plain"
              >
                <v-row>
                  <v-col cols="12">
                    <v-text-field flat label="Name*" solo></v-text-field>
                  </v-col>

                  <v-col cols="12">
                    <v-text-field flat label="Email*" solo></v-text-field>
                  </v-col>

                  <v-col cols="12">
                    <v-text-field flat label="Subject*" solo></v-text-field>
                  </v-col>

                  <v-col cols="12">
                    <v-textarea flat label="Message*" solo></v-textarea>
                  </v-col>

                  <v-col class="mx-auto" cols="auto">
                    <v-btn type="submit" value="Send" color="accent" x-large>
                      Submit
                    </v-btn>
                  </v-col>
                </v-row>
              </form>
            </v-theme-provider>
          </v-col>
        </v-row>
      </v-container>

      <div class="py-12"></div>
    </v-sheet>
  </v-content>
</template>
<style scoped>
a {
  word-break: break-all;
}
</style>
