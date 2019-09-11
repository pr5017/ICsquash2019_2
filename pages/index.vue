/*Html for home page*/
<template>
  <div class="container">

    <div class="container">
      <v-jumbotron>
        <v-container>
          <v-layout align-center>
            <v-btn
              id="join_us"
              round
              small
              color="beige lighten-3"
              absolute
              @click=""
              href="/join_us"
            >Join Us
            </v-btn>
          </v-layout>
        </v-container>
      </v-jumbotron>
    </div>

    <div class="container">
      <v-layout column align-center>
        <h class="head-about_us">About Us</h>
        <v-container>
          <p class="blockquote justify-space-around">
            By joining
            <b>Imperial Squash</b> you can play squash at any level.
          </p>
          <p
            class="blockquote"
          >We offer something for everyone, whether it is playing competitively with the teams or participating as a casual social member.</p>
          <p class="blockquote">
            Courts are right at the heart of the South Kensington campus at
            <b>Ethos Sports Centre</b> becoming a member lets you book free courts throughout the year.
          </p>

          <p class="blockquote">
            Playing competitively for the teams also allows you to attend team training sessions.
            There are four Men’s teams and two Women’s teams.
            <v-spacer>In addition to these competitive and social sessions, there are also special squash events throughout the year, including a doubles tournament.</v-spacer>
          </p>
          <p class="blockquote">
            Other
            <b>social events</b> include pub crawls, boozy bowling, sports’ nights, and club dinners. So no matter your level, the Squash Club definitely has something to offer.
          </p>
          <v-icon color="teal lighten-2">{{icon}}</v-icon>
        </v-container>
      </v-layout>
    </div>

  </div>
</template>

/*Style for home page*/

<style lang="stylus" scoped>

#join_us {
  left: 50%;
  top: 250px;
  transform: translate(-50%, -50%);
  min-height: 5%;
  width: 250px;
  max-width: 25%;
  padding: 5px;
  font-size: 15px;
  opacity: 0.9;
  background-color: #eceff1;
  font-family: 'Courier New';
}

.clickable {
  cursor: pointer;
}

/* Small devices (portrait tablets and large phones, 600px and up) */
@media only screen and (min-width: 600px) {

}

/* Medium devices (landscape tablets, 768px and up) */
@media only screen and (min-width: 768px) {

}

/* sub class Med-Large */
@media only screen and (min-width: 960px) {

}

</style>

/*Script for home page*/

<script>
export default {
  computed: {
    currentBreakPoint() {
      return this.$vuetify.breakpoint.name;
    }
  },
  mounted() {
    this.screenSize = this.currentBreakPoint;
    console.log("init", this.screenSize);
  },
  methods: {
    shop() {
      window.location.href =
        "https://www.imperialcollegeunion.org/activities/a-to-z/squash";
    }
  },
  watch: {
    currentBreakPoint() {
      console.log("changed1", this.screenSize);

      this.screenSize = this.currentBreakPoint;
      console.log("changed2", this.screenSize);
    },
    screenSize() {
      switch (this.screenSize) {
        case "xs":
          return (this.featuredphotos = "277px");
        case "sm":
          return (this.featuredphotos = "450px");
        case "md":
          return (this.featuredphotos = "768px");
      }
    }
  }
};

</script>
