<template>
  <div>
    <release-header
      header="Version 14 - War Manager Fenix (v2.8.14)"
      subtitle="Bugs fixed, user messaging functionality, ground work laid for csv importing tool (forms system), and introduced War Manager Open Beta."
    ></release-header>
    <v-row align="center" justify="center">
      <v-col>
        <v-tooltip v-for="item in releaseTypes" :key="item" bottom>
          <template v-slot:activator="{ on, attrs }">
            <v-chip
              class="mr-5"
              :color="item.color"
              outlined
              v-bind="attrs"
              v-on="on"
              ><v-icon left>{{ item.icon }}</v-icon
              >{{ item.title }}</v-chip
            >
          </template>
          <span>{{ item.description }}</span>
        </v-tooltip>
        <div class="my-5" />
        <v-card>
          <v-card-title compact> Change Log </v-card-title>
          <v-card-text>
            <v-list dense>
              <v-list-item v-for="changeLog in changeLogs" :key="changeLog">
                {{ changeLog }}
              </v-list-item>
            </v-list>
          </v-card-text>
        </v-card>
        <div class="my-5" />
        <v-card>
          <v-card-title>Known Issues</v-card-title>
          <v-card-text>
            <ol>
              <li>
                Accessing the button links is impossible when using touch screen
                - working on a fix
              </li>
              <li>
                Having admin privilege does not guarantee that all sheets and
                datasets will show up (a.k.a. permissions system working too
                well)
              </li>
              <li>Need feature to add/remove datasets from sheets</li>
              <li>
                Issue when cards' dataset is removed from a sheet, the card is
                not locked
              </li>
              <li>Selecting cards sometimes bugs out</li>
            </ol>
          </v-card-text>
          <v-divider />
          <v-card-actions>
            <v-spacer />
            <bug-report-component />
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import BugReportComponent from '~/components/BugReportComponent.vue'
export default {
  name: 'ReleaseVersion2814',
  components: { BugReportComponent },
  data() {
    return {
      releaseTypes: [
        {
          icon: 'mdi-calendar-check',
          color: 'purple',
          title: '1.5.2022',
          description: 'Release Date',
        },
        {
          title: 'minor update',
          icon: 'mdi-update',
          color: 'green',
          description: 'Minor updates add small features and fix deep bugs',
        },
        {
          title: 'Bug Fix',
          icon: 'mdi-bug-check',
          color: 'red',
          description: 'Bugs were fixed in this update',
        },
      ],
      changeLogs: [
        '1. Started work on forms tool',
        "2. Added 'user-to-user' messaging functionality for better coordination",
        '3. Fixed issue where hovering over a button link would not show the button link',
        '4. Changed process to open a link: In order to activate the button link, press alt + left mouse click',
        '5. Fixed issue where button link would not activate',
        '6. Fixed issue where the loading UI widget would get stuck if an error was thrown',
        '7. Fixed issue where after creating editing data would cause the user to get thrown back to the home menu',
      ],
    }
  },
}
</script>

<style>
</style>