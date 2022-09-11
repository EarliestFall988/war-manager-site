<template>
  <v-tooltip bottom>
    <template v-slot:activator="{ on, attrs }">
      <v-btn to="/reportBugForm" link rounded v-bind="attrs" v-on="on"
        ><v-icon>mdi-bug</v-icon>Report Bug</v-btn
      >
    </template>
    <span>Found a bug? Report it here</span>
  </v-tooltip>
</template>

<script>
export default {
  name: 'BugReportComponent',
}
</script>

<style>
</style>