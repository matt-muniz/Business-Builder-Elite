<template>
  <div>
    <Hero />
    <Info />
  </div>
</template>

<script>
import Hero from "~/components/hero.vue";
import Info from "~/components/info.vue";

export default {
  components: {
    Hero,
    Info
  },
  data() {
    return {};
  }
};
</script>
