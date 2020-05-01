<template>
  <v-img
    class="image_bg"
    :src="resize.image"
    :aspect-ratio="resize.aspectRatio"
    alt=""
  >
    <div class="hero body">
      <!-- System Bar -->
      <v-system-bar class="pt-5" height="auto" :color="color">
        <img class="mr-6" src="~/assets/facebook.svg" />
        <img class="mr-6" src="~/assets/instagram.svg" />
        <img class="mr-6" src="~/assets/twitter.svg" />
        <img src="~/assets/linkedin.svg" />
        <v-spacer></v-spacer>
        <a href="mailto:socialmediateam@businessbuilderelite.com" class="mr-11"
          ><img
            class="mr-1"
            src="~/assets/email.svg"
          />socialmediateam@businessbuilderelite.com</a
        >
        <a href="tel:9783252105"
          ><img class="mr-1" src="~/assets/phone.svg" />978-325-2105</a
        >
      </v-system-bar>
      <!-- App Bar -->
      <v-app-bar
        class="app-bar pa-0"
        style="margin-top: 94px"
        flat
        :color="color"
      >
        <img class="mr-1" src="~/assets/logo.svg" />
        <span class="display-2 font-weight-black" style="color: #176D96"
          >Business Builder Elite</span
        >
        <v-spacer></v-spacer>
        <v-list v-if="this.$vuetify.breakpoint.lgAndUp" :color="color" flat
          ><v-list-item-group>
            <v-list-item
              v-for="(item, i) in navLinks"
              :key="i"
              class="text-right d-inline-flex font-weight-black"
              active-class="highlighted"
              nuxt
              :to="item.to"
            >
              <v-list-item-content>
                <v-list-item-title v-text="item.title"></v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list-item-group>
        </v-list>
      </v-app-bar>
    </div>
  </v-img>
</template>

<script>
export default {
  data() {
    return {
      color: "rgba(0,0,0,0)",
      xsOnly: null,
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
      ],
      desktop_bg: {
        image: require("../assets/bg.png"),
        aspectRatio: 2
      },
      tablet_bg: {
        image: require("../assets/bg.png"),
        aspectRatio: 1.3
      },
      mobile_bg: {
        image: require("../assets/mobile_bg.png"),
        aspectRatio: 1
      }
    };
  },
  computed: {
    resize() {
      if (this.$vuetify.breakpoint.xsOnly) {
        return {
          image: this.mobile_bg.image,
          aspectRatio: this.mobile_bg.aspectRatio
        };
      } else if (this.$vuetify.breakpoint.xlOnly) {
        return {
          image: this.desktop_bg.image,
          aspectRatio: this.desktop_bg.aspectRatio
        };
      } else {
        return {
          image: this.tablet_bg.image,
          aspectRatio: this.tablet_bg.aspectRatio
        };
      }
    }
  }
};
</script>

<style scoped>
a {
  text-decoration: none;
  color: white;
}
.hero {
  /* min-height: 100%; */
  /* background: radial-gradient(#7465a7, #3a3354); */
  overflow: hidden;
}
</style>
