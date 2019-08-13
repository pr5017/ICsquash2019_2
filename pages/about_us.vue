<template>
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
</template>

<style>
.layout {
  background-color: papayawhip;
  height: 100%;
  opacity: 10%;
}
.head-about_us {
  font-size: 40px;
  font-weight: 900;
  margin: 80px 30px 10px 30px;
}
.v-container {
  background-color: darkblue;
}
p {
  text-align: center;
  font-size: 18px;
  margin: 5px 100px;
  padding: 5px 100px;
}

/* Small devices (portrait tablets and large phones, 600px and up) */
@media only screen and (min-width: 600px) {
}
/* Medium devices (landscape tablets, 768px and up) */
@media only screen and (min-width: 768px) {
  .head-about_us {
    font-size: 60px;
  }
  .content-about_us {
    font-size: 20px;
    margin: 20px;
    padding: 15px 30px 0px 30px;
  }
}
/* Large devices (laptops/desktops, 1280px and up) */
@media only screen and (min-width: 1280px) {
  .head-about_us {
    font-size: 100px;
  }
  .content-about_us {
    font-size: 20px;
    margin: 5px 200px;
    padding: 10px 20px;
  }
}
</style>


