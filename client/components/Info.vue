<template>
  <div
    :class="{
      desktop_body: $vuetify.breakpoint.lgAndUp,
      mobile_body: $vuetify.breakpoint.mdAndDown
    }"
  >
    <v-row>
      <v-col cols="12" md="6">
        <v-row
          justify="center"
          justify-md="start"
          justify-xl="center"
          class="mr-1"
        >
          <v-card
            class="website"
            :class="{
              website_mobile: $vuetify.breakpoint.smAndDown,
              website_other: $vuetify.breakpoint.mdAndUp
            }"
            width="100%"
            max-width="670"
          >
            <div
              v-if="$vuetify.breakpoint.smAndUp"
              class="mt-10"
              style="height: 250px"
            >
              <v-img contain height="100%" src="/deskop_views.svg"></v-img>
            </div>
            <div v-else class="mt-10" style="height: 100px">
              <v-img contain height="100%" src="/mobile_views.svg"></v-img>
            </div>
            <v-card-text>
              hello
            </v-card-text>
          </v-card>
        </v-row>
      </v-col>
      <v-col cols="12" md="6">
        <v-row justify="center" justify-md="end" justify-xl="center">
          <v-card
            class="social"
            :class="{
              social_mobile: $vuetify.breakpoint.smAndDown,
              social_other: $vuetify.breakpoint.mdAndUp
            }"
            width="100%"
            max-width="670"
          >
            <v-img max-height="320" src="social_bg.jpg"></v-img>

            <v-card-text>
              hello
            </v-card-text>
          </v-card>
        </v-row>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {};
</script>

<style>
.website_mobile {
  margin-top: 3.5rem;
}
.website_other {
  margin-top: 7rem;
}
.social_mobile {
  margin-top: 1.25rem;
  margin-bottom: 3.5rem;
}
.social_other {
  margin-top: 23.75rem;
  margin-bottom: 7rem;
}
</style>
