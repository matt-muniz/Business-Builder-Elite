<template>
  <v-app dark>
    <v-content>
      <nuxt />
    </v-content>

    <Footer />
  </v-app>
</template>

<script>
import Footer from "~/components/footer.vue";

export default {
  components: {
    Footer
  },
  data() {
    return {};
  }
};
</script>

<style>
.body {
  padding: 0 126px;
}
.v-toolbar__content {
  padding: 0;
}
.v-tabs {
  width: 0;
}
.v-list-item__content .v-list-item__title {
  color: #176d96;
  overflow: visible;
  position: relative;
}
.v-list-item__title:hover {
  color: #176d96;
}
.highlighted .v-list-item__title::after {
  content: "";
  position: absolute;
  bottom: -5px;
  left: 0;
  border: 2px solid #7bc7f0;
  z-index: 100;
  animation: slide 2s forwards;
}
@keyframes slide {
  from {
    width: 0;
    opacity: 0;
  }
  to {
    width: 100%;
    opacity: 1;
  }
}
</style>
