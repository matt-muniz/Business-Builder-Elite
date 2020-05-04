<template>
  <div>
    <v-system-bar class="pt-5 px-0" height="auto" :color="color">
      <img class="mr-6" src="~/assets/facebook.svg" />
      <img class="mr-6" src="~/assets/instagram.svg" />
      <img class="mr-6" src="~/assets/twitter.svg" />
      <img src="~/assets/linkedin.svg" />
      <v-spacer></v-spacer>
      <div v-if="resize.showListItems">
        <a href="mailto:socialmediateam@businessbuilderelite.com" class="mr-11"
          ><img
            class="mr-1"
            src="~/assets/email.svg"
          />socialmediateam@businessbuilderelite.com</a
        >
        <a href="tel:9783252105"
          ><img class="mr-1" src="~/assets/phone.svg" />978-325-2105</a
        >
      </div>
      <div v-else>
        <v-menu
          attach=".v-system-bar"
          absolute
          transition="slide-y-transition"
          min-width="100%"
          :nudge-bottom="height"
        >
          <template v-slot:activator="{ on }">
            <v-btn
              style="color: #176D96"
              depressed
              color="rgba(0,0,0,0)"
              class="white--text"
              v-on="on"
            >
              <span v-if="$vuetify.breakpoint.smAndUp" class="mr-1"
                >Contact</span
              >
              <span v-else class="mr-1 caption">Contact</span>
              <img src="~/assets/arrow-dropdown.svg" />
            </v-btn>
          </template>
          <v-list flat color="rgba(0,0,0,0.7)"
            ><v-list-item-group>
              <v-list-item
                class="text-right font-weight-black"
                href="mailto:socialmediateam@businessbuilderelite.com"
              >
                <v-list-item-content
                  :class="{ mobileTitle: $vuetify.breakpoint.mdAndDown }"
                >
                  <v-list-item-title class="mr-3 white--text"
                    ><img
                      class="mr-1"
                      src="~/assets/email.svg"
                    />socialmediateam@businessbuilderelite.com</v-list-item-title
                  >
                </v-list-item-content>
              </v-list-item>
              <v-list-item
                class="text-right font-weight-black"
                href="tel:9783252105"
              >
                <v-list-item-content
                  :class="{ mobileTitle: $vuetify.breakpoint.mdAndDown }"
                >
                  <v-list-item-title class="mr-3 white--text"
                    ><img
                      class="mr-1"
                      src="~/assets/phone.svg"
                    />978-325-2105</v-list-item-title
                  >
                </v-list-item-content>
              </v-list-item>
            </v-list-item-group>
          </v-list>
        </v-menu>
      </div>
    </v-system-bar>
    <!-- App Bar -->
    <v-app-bar
      class="app-bar pa-0"
      :class="{
        mobile: $vuetify.breakpoint.smAndDown,
        desktop: $vuetify.breakpoint.mdAndUp
      }"
      flat
      :color="color"
    >
      <img
        v-if="$vuetify.breakpoint.mdAndUp"
        class="logo mr-1"
        src="~/assets/logo.svg"
      />
      <img v-else class="logo mr-1" src="~/assets/mobile_logo.svg" />
      <span
        class="font-weight-black"
        :class="{
          'display-3': $vuetify.breakpoint.mdAndUp,
          title: $vuetify.breakpoint.smAndDown
        }"
        style="color: #176D96"
        >Business Builder Elite</span
      >
      <v-spacer></v-spacer>
      <v-list v-if="resize.showListItems" :color="color" flat
        ><v-list-item-group>
          <v-list-item
            v-for="(item, i) in navLinks"
            :key="i"
            class="text-right d-inline-flex font-weight-black pr-0 pl-12"
            active-class="highlighted"
            nuxt
            :to="item.to"
          >
            <v-list-item-content>
              <v-list-item-title
                :class="{ desktoptitle: $vuetify.breakpoint.lgAndUp }"
                v-text="item.title"
              ></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
      <div v-else-if="$vuetify.breakpoint.mdAndDown">
        <v-menu
          attach=".v-toolbar__content"
          absolute
          transition="slide-y-transition"
          min-width="100%"
          :nudge-bottom="height"
        >
          <template v-slot:activator="{ on }">
            <v-btn
              style="color: #176D96"
              depressed
              color="rgba(0,0,0,0)"
              v-on="on"
            >
              <v-icon>mdi-menu</v-icon>
            </v-btn>
          </template>
          <v-list flat color="rgba(0,0,0,0.7)"
            ><v-list-item-group>
              <v-list-item
                v-for="(item, i) in navLinks"
                :key="i"
                class="text-right font-weight-black"
                active-class="highlighted"
                nuxt
                :to="item.to"
              >
                <v-list-item-content
                  :class="{ mobileTitle: $vuetify.breakpoint.mdAndDown }"
                >
                  <v-list-item-title
                    class="mr-3"
                    v-text="item.title"
                  ></v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list-item-group>
          </v-list>
        </v-menu>
      </div>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  props: ["resize"],
  data() {
    return {
      color: "rgba(0,0,0,0)",
      height: "75",
      navLinks: [
        {
          title: "Home",
          to: "/"
        },
        {
          title: "About Us",
          to: "/about"
        },
        {
          title: "Portfolio",
          to: "/portfolio"
        },
        {
          title: "Services",
          to: "/services"
        }
      ]
    };
  }
};
</script>

<style scoped>
a {
  text-decoration: none;
  color: white;
  padding: 0;
}
.mobile {
  margin-top: 24px !important;
}
.desktop {
  margin-top: 94px !important;
}
.v-menu__content {
  box-shadow: none;
}
.highlighted .mobileTitle {
  background: rgba(0, 0, 0, 0.1);
}
</style>
