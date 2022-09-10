<template>
  <v-row>
    <v-col>
      <v-card elevation="2" shaped>
        <div class="my-5">
          <h1 class="pt-5 pl-7">About</h1>
          <v-alert
            v-for="alert in alerts"
            :key="alert"
            border="left"
            color="blue"
            text
            class="my-5 mx-5 px-5"
          >
            {{ alert.message }}
          </v-alert>
        </div>

        <v-divider></v-divider>
        <v-card-actions>
          <v-spacer />
          <v-btn color="blue" to="/contact">Contact</v-btn>
          <v-btn color="blue" text href="https://jrcousa.com" class="my-5 mx-5"
            >Have Questions about your roof?</v-btn
          >
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'AboutPage',
  data() {
    return {
      alerts: [
        {
          message:
            'War Manager is a logistics tool developed by Taylor Howell for JR&CoLLC. roofing contractors. If you are not affiliated with JR&CO LLC. and are interested in War Manager, reach out to Taylor at taylor.howell@jrcousa.com',
        },
        {
          message:
            'The War Manger Website was also developed by Taylor Howell - if you have any questions, comments, or concerns, contact Taylor at taylor.howell@jrcousa.com The War Manager logo, the War Manager Triangle, the JR&Co logo and all derivative works are property of JR&Co LLC.',
        },
      ],
    }
  },
}
</script>

<style>
</style>