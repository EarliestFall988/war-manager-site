<template>
  <v-row justify="centered" align="center">
    <v-col cols="12">
      <div id="bg">
        <h1>{{ header }}</h1>
        <div id="cont">
          <span id="sub">{{ date }}</span>
          <p id="bottom">TLDR: {{ subtitle }}</p>
        </div>
      </div>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'ReleaseHeaderComponent',
  props: {
    header: {
      type: String,
      default: 'War Manager Release',
    },
    date: {
      type: String,
      default: '',
    },
    subtitle: {
      type: String,
      default: '',
    },
  },
}
</script>

<style>
#sub {
  color: #777;
  font-weight: light;
}
#bottom {
  font-size: 1.25em;
  color: #2b81d6;
}

#cont {
  display: flex;
  flex-direction: column;
}

#bg {
  background-color: #222;
  padding: 0.25em;
  padding-left: 1em;
  padding-right: 1em;
  border-left: 4px solid #444;
}
</style>

