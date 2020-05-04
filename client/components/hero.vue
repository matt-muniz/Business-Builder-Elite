<template>
  <client-only>
    <v-img
      class="image_bg"
      :src="resize.image"
      :aspect-ratio="resize.aspectRatio"
      alt=""
    >
      <div
        :class="{
          desktop_body: $vuetify.breakpoint.lgAndUp,
          mobile_body: $vuetify.breakpoint.mdAndDown
        }"
      >
        <Nav :resize="resize" />
        <div
          class="heading-1"
          :class="{
            mobile: $vuetify.breakpoint.xsOnly,
            heading1Mobile: $vuetify.breakpoint.xsOnly,
            heading1Desktop: $vuetify.breakpoint.smAndUp
          }"
        >
          <span
            class="heading"
            :class="{
              'display-3': $vuetify.breakpoint.smAndUp,
              headline: $vuetify.breakpoint.xsOnly
            }"
            >Stop Struggling <br />
            To Generate New <br />Business</span
          >
        </div>
        <div
          class="heading-2"
          :class="{
            mobile: $vuetify.breakpoint.xsOnly,
            heading2Mobile: $vuetify.breakpoint.xsOnly,
            heading2Desktop: $vuetify.breakpoint.smAndUp
          }"
        >
          <span
            class="heading"
            :class="{
              headline: $vuetify.breakpoint.smAndUp,
              'subtitil-1': $vuetify.breakpoint.xsOnly
            }"
          >
            Learn Our Prove Strategy <br />
            For Driving In New Leads
          </span>
        </div>
        <div
          class="cta"
          :class="{
            mobile: $vuetify.breakpoint.xsOnly,
            ctaMobile: $vuetify.breakpoint.xsOnly,
            ctaDesktop: $vuetify.breakpoint.smAndUp
          }"
        >
          <span
            class="font-weight-black ctaTitle"
            :class="{
              title: $vuetify.breakpoint.smAndUp,
              caption: $vuetify.breakpoint.xsOnly
            }"
          >
            Book A Free <br />
            Consultation Today
          </span>
          <div
            :class="{
              mobileBtn: $vuetify.breakpoint.xsOnly,
              desktopBtn: $vuetify.breakpoint.smAndUp
            }"
          >
            <v-btn class="white--text" color="#176d96" depressed
              >Book Now</v-btn
            >
          </div>
        </div>
      </div>
    </v-img>
  </client-only>
</template>

<script>
import Nav from "@/components/Nav";

export default {
  components: {
    Nav
  },
  data() {
    return {
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
          aspectRatio: this.mobile_bg.aspectRatio,
          body: true
        };
      } else if (this.$vuetify.breakpoint.lgAndUp) {
        return {
          image: this.desktop_bg.image,
          aspectRatio: this.desktop_bg.aspectRatio,
          showListItems: true
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
.mobile {
  text-align: center;
}
.heading-1 {
  color: #7eb7cd;
}
.heading1Desktop {
  margin-top: 6.875rem;
}
.heading1Mobile {
  margin-top: 2.25rem;
}
.heading-1 .display-3 {
  line-height: 5rem;
  font-weight: bold;
}
.heading-2 {
  color: #7eb7cd;
}
.heading2Desktop {
  margin-top: 4.6875rem;
}
.heading2Mobile {
  margin-top: 1.125rem;
}
.ctaDesktop {
  margin-top: 9.375rem;
}
.ctaMobile {
  margin-top: 3.5625rem;
}
.ctaTitle {
  color: #176d96;
}
.desktopBtn {
  margin-top: 2.5rem;
  margin-bottom: 5.125rem;
}
.mobileBtn {
  margin-top: 0.625rem;
  margin-bottom: 3.125rem;
}
.hero {
  overflow: hidden;
}
</style>
