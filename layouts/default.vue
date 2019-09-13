<template>
  <v-app class="grey lighten-4">
      <TheNavbar/>
      <nuxt/>
      <pageBottom/>
  </v-app>
</template>

<style>

  h1 {
    font-size: 3em;
  }

  h2 {
    font-size: 2.5em;
  }

  ol {
    font-size: 1.5em;
  }

  .blockquote {
    font-size: 1.5em;
  }
</style>

<script>

  import TheNavbar from "@/components/TheNavbar"
  import pageBottom from "@/components/pageBottom"

  export default {

    components: {
      TheNavbar,
      pageBottom
    },

    data() {
      return {
        clipped: false,
        drawer: false,
        fixed: false,
        items: [
          {
            icon: 'apps',
            title: 'Welcome',
            to: '/'
          },
          {
            icon: 'bubble_chart',
            title: 'Inspire',
            to: '/inspire'
          }
        ],
        miniVariant: false,
        right: true,
        rightDrawer: false,
        title: 'Vuetify.js'
      }
    }
  }
</script>
