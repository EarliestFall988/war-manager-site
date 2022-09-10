<template>
  <v-row justify="center" align="center">
    <v-col cols="8" sm="5" md="5" lg="4">
      <h1>Contact</h1>
      <v-card elevation="4" shaped>
        <v-img :src="require('@/static/assets/taylor.png')" height="300px" />
        <v-card-title> Taylor Howell </v-card-title>
        <v-card-subtitle>Software Engineer</v-card-subtitle>
        <v-card-text
          >Responsible for full stack development on War Manager.</v-card-text
        >
        <v-card-actions>
          <v-spacer />
          <v-btn
            v-for="chip in taylor_contact"
            :key="chip"
            rounded
            color="blue"
            outlined
            @click.stop="
              ;(setText = chip.content),
                (headerText = chip.title),
                (dialog = true)
            "
            ><v-icon>{{ chip.icon }}</v-icon>
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>

    <v-dialog v-model="dialog" max-width="290">
      <v-card>
        <v-card-title class="headline">{{ headerText }}</v-card-title>

        <v-card-text> {{ setText }} </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn rounded text color="blue" @click.stop="dialog = false"
            >Close</v-btn
          >
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>

<script>
export default {
  name: 'ContactPage',
  data() {
    return {
      dialog: false,
      headerText: '',
      setText: '',
      taylor_contact: [
        {
          icon: 'mdi-email',
          title: 'Email',
          content: 'howelltaylor195@gmail.com',
          to: '',
        },
        {
          icon: 'mdi-phone',
          title: 'Phone',
          content: '(123) 456-7890',
        },
      ],
    }
  },
}
</script>

<style>
</style>