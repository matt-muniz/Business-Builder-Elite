<template>
  <v-img
    class="image_bg"
    :src="desktop_bg.image"
    :aspect-ratio="desktop_bg.aspectRatio"
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
        <v-list :color="color" flat
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
      mobile_bg: {
        image: require("../assets/mobile_bg.png"),
        aspectRatio: 1
      }
    };
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
