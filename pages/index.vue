/*Html for home page*/
<template>
  <div class="main">
    <div class="main" id="jumbo">
      <div id="topPart">
        <img src="/logo-shadow.png" alt="" id="logo">
      </div>
      <div id="bottomPart">
          <img src="/IC_Logo.png" id="iclogo">
          <v-row>
            <v-flex text-xs-center>
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
            </v-flex>
          </v-row>
      </div>
    </div>

    <div class="container">
      <v-layout column align-center>
        <h2 class="head-about_us">About Us</h2>
        <v-container>
          <p class="blockquote justify-space-around">
            At Imperial Squash, our <b>main</b> aim is to <b>build</b> the squash community at Imperial College.
             Whether it is playing <b>competitively</b> with the teams, participating as a <b>casual</b> social member <b>or</b>
             holding a raquet for the first time as a <b>beginner</b> we hope to see <b>you</b> on court.</p>
          <p class="blockquote">
            Becoming a member of <b>this</b> society allows you to book <b>free</b> courts during the year.
              Membership also allows you to come to the <b>regular</b> social sessions, where you can meet new people with varying levels of experiences and have fun. There will also be members of
              the competitive teams who can provide <b>coaching and tips</b>.
          </p>

          <p class="blockquote">
            <v-spacer>In addition to these sessions, there are also special squash events throughout the year, including a doubles tournament and mini-league.</v-spacer>
          </p>

          <p class="blockquote">
            Other <b>social events</b> include pub crawls, bowling, game's night, sports’ nights, and club dinners. So no matter your level, the we definitely have something to offer.
          </p>
        </v-container>

        <h2>Where to find us</h2>
        <v-container>
          <p class="blockquote">
              Courts are right at the heart of the South Kensington campus at <b>Ethos Sports Centre</b> (7 Princes Gardens, Knightsbridge, London SW7 1NA).
          </p>
        </v-container>

        <h2>Competitive Squash</h2>
        <v-container>
          <p class="blockquote">
            If you are looking to play more competitively we have two women's teams and four men's teams. The teams compete in the BUCS and LUSL leagues with <b>regular</b> matches across
            London and the country.
          </p>
          <p class="blockquote">
            Joining the team allows you to attend team training sessions as well as additional benefits such as strength and conditioning.
            In order to join, make sure you attend the team trials at the beginning of the autumn and spring term! To find out more details please contact comittee members
            via email or facebook.
          </p>
        </v-container>

      </v-layout>
    </div>

  </div>
</template>

/*Style for home page*/

<style lang="stylus" scoped>

.main {
  width: 100%;
}

#logo {
  height: 100%;
}

#iclogo {
  height: 40%;
  margin: 1%;
}

#topPart {
  height: 50%;
}

#bottomPart {
  height:50%;
  text-align: center;
}

#jumbo {
  background-image: linear-gradient(to top, rgba(255, 255, 255, 0.6), rgba(0, 0, 0, 0.8)), url("../assets/seigo.jpg");
  background-size: cover;
  background-attachment: fixed;
  height: 724px;
  text-align: center;
  padding-top: 50px;
}

#join_us {
  transform: translate(-50%, -50%);
  height:3%
  width: 250px;
  max-width: 25%;
  padding: 5px;
  font-size: 15px;
  opacity: 0.9;
  background-color: #eceff1;
  font-family: 'Courier New';
  margin-top: 30px;
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
  data: () => ({
  }),
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
