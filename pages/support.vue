<template>
  <v-row justify="centered" align="center">
    <v-col cols="12" lg="10">
      <h2 class="my-2 text-center">Support</h2>

      <p class="py-1 text-center">
        Here, you can look at helpful videos, release information, and create
        bug reports.
      </p>

      <div class="my-10">
        <v-row justify="space-around" align="center">
          <v-btn
            v-for="link in options"
            :key="link"
            :to="to"
            justify="center"
            align="center"
            color="primary"
            ><v-icon medium>{{ link.icon }}</v-icon> {{ link.title }}</v-btn
          >
        </v-row>
      </div>

      <div class="mx-20" />
      <v-banner outlined rounded text>Latest Release Info</v-banner>
    </v-col>
    <v-col v-for="info in releaseInfos" :key="info" cols="12" md="6" lg="5">
      <v-card outlined>
        <v-card-title>{{ info.title }}</v-card-title>
        <v-card-subtitle>{{ info.subtitle }}</v-card-subtitle>
        <v-card-text>{{ info.content }}</v-card-text>

        <v-divider />
        <v-card-actions>
          <v-chip
            v-for="tag in info.tags"
            :key="tag"
            outlined
            :color="tag.color"
          >
            <v-icon left>{{ tag.icon }}</v-icon> {{ tag.title }}
          </v-chip>
          <v-spacer />
          <div v-if="info.to">
            <v-tooltip bottom>
              <template v-slot:activator="{ on, attrs }">
                <v-btn
                  color="primary"
                  dark
                  :to="info.to"
                  v-bind="attrs"
                  v-on="on"
                  ><v-icon>mdi-arrow-right</v-icon></v-btn
                >
              </template>
              <span>Read More: {{ info.title }}</span>
            </v-tooltip>
          </div>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'SupportPage',
  data() {
    return {
      options: [
        {
          icon: 'mdi-information',
          title: 'Releases',
          to: '#!',
        },
        {
          icon: 'mdi-video',
          title: 'Videos',
          to: '#!',
        },
        {
          icon: 'mdi-bug',
          title: 'Report Bug',
          to: '#!',
        },
      ],
      releaseInfos: [
        {
          title: 'Version 14 Release (v2.8.14)',
          subtitle: '1.5.2022',
          content:
            'Bugs fixed, user messaging functionality, ground work laid for csv importing tool (forms system), and introduced War Manager Open Beta.',
          to: '/ReleaseInfo/Release_v2_8_14',
          tags: [
            {
              title: 'minor update',
              icon: 'mdi-update',
              color: 'green',
              description: 'Minor updates add small features and fix deep bugs',
            },
          ],
        },
        {
          title: 'Version 14 Release (v2.9.14h1)',
          subtitle: '1.7.2022',
          content: 'Hotfix',
          to: '/ReleaseInfo/version_2_8_14_h1',
          tags: [{ title: 'hotfix', icon: 'mdi-fire', color: 'orange' }],
        },
        {
          title: 'War Manager Release v2.9.2',
          subtitle: '2.19.22',
          content: 'this is more information about the release',
          to: '/ReleaseInfo/warmanagerreleasetemplate',
          tags: [{ title: 'hotfix', icon: 'mdi-fire', color: 'orange' }],
        },
      ],
    }
  },
}
</script>

<style>
</style>