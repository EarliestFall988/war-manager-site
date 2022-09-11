<template>
  <v-row align="center" justify="center">
    <v-col cols="12">
      <v-card>
        <v-card-title><v-icon>mdi-bug</v-icon>Report Bug</v-card-title>
        <v-card-subtitle
          >Found something that is broken, or just doesn't seem right? Let us
          know here.</v-card-subtitle
        >
      </v-card>
      <v-container>
        <v-form ref="form" v-model="valid" lazy-validation>
          <v-col cols="5">
            <v-text-field
              v-model="name"
              :rules="nameRules"
              :counter="20"
              label="Name"
              clearable
              filled
              required
            ></v-text-field>
            <v-text-field
              v-model="email"
              :rules="emailRules"
              label="E-mail"
              clearable
              filled
              required
            ></v-text-field>
            <v-textarea
              v-model="description"
              multi-line="true"
              :counter="144"
              clearable
              label="What happened?"
              required
              filled
            ></v-textarea>
            <v-select
              :items="bugTypes"
              label="How often does this happen?"
              filled
            />
            <v-btn color="blue" @click="validate">File Report</v-btn>
            <v-btn rounded text @click="reset">Reset</v-btn>
          </v-col>
        </v-form>
      </v-container>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'ReportBugForm',
  data: () => ({
    valid: true,
    name: '',
    nameRules: [
      (v) => !!v || 'Name is required',
      (v) => (v && v.length <= 20) || 'Name must be less than 20 characters',
    ],
    email: '',
    emailRules: [
      (v) => !!v || 'E-mail is required',
      (v) => /.+@.+\..+/.test(v) || 'E-mail must be valid',
    ],
    select: null,
    items: ['Item 1', 'Item 2', 'Item 3', 'Item 4'],
    bugTypes: ['Always', 'Sometimes', 'Usually', 'Once in a while'],
    checkbox: false,
    lazy: false,
  }),
  methods: {
    validate() {
      this.$refs.form.validate()
    },
    reset() {
      this.$refs.form.reset()
    },
    resetValidation() {
      this.$refs.form.resetValidation()
    },
  },
}
</script>

<style>
</style>