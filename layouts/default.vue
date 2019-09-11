<template>
  <v-app class="grey lighten-4">
    <div class="container">
      <TheNavbar/>
      <nuxt/>
    </div>
  </v-app>
</template>

<script>

  import TheNavbar from "@/components/TheNavbar"

  export default {

    components: {
      TheNavbar
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
