<template>
  <div>
    <release-header
      header="Version 14 - War Manager Fenix (v2.8.14h1)"
      subtitle="Bugs fixed"
    ></release-header>
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
    <v-row align="center" justify="center">
      <v-col>
        <v-card>
          <v-card-title> Change Log </v-card-title>
          <v-card-text>
            <ol>
              <li>Started work on forms tool</li>
              <li>
                Added 'user-to-user' messaging functionality for better
                coordination
              </li>
              <li>
                Fixed issue where hovering over a button link would not show the
                button link
              </li>
              <li>
                Changed process to open a link: In order to activate the button
                link, press alt + left mouse click
              </li>
              <li>Fixed issue where button link would not activate</li>
              <li>
                Fixed issue where the loading UI widget would get stuck if an
                error was thrown
              </li>
              <li>
                Fixed issue where after creating editing data would cause the
                user to get thrown back to the home menu
              </li>
            </ol>
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
  components: { BugReportComponent },
  name: 'ReleaseVersion2814',
  data() {
    return {
      releaseTypes: [
        {
          icon: 'mdi-calendar-check',
          color: 'purple',
          title: '1.7.2022',
          description: 'Release Date',
        },
        {
          icon: 'mdi-fire',
          title: 'hotfix',
          color: 'orange',
          description:
            'Breaking bugs or tweaks found upon release are fixed usually within a month after release',
        },
        {
          title: 'Bug Fix',
          icon: 'mdi-bug-check',
          color: 'red',
          description: 'Bugs were fixed in this update',
        },
      ],
    }
  },
}
</script>

<style>
</style>