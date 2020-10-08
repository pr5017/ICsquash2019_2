<template>

  <div class="main" id="footer">
    <div class="container">
      <h2>Contacts</h2>
      <img src="../assets/ICU_logo.png" alt="" id="footerLogo">
      <img src="../assets/sport_imperial_logo.jpg" alt="" id="footerLogo">
      <p id="ICemail"><b>Email:</b> squash@ic.ac.uk</p>
      <a href="https://l.facebook.com/l.php?u=https%3A%2F%2Fsites.google.com%2Fview%2Fic-squash-pp-2020-21%2Fhome%3Ffbclid%3DIwAR2nnVNfYpgEAAqUGjTbAgrzhkKUqb_x5Od9NXId3Uw_9Tbxx1MCrXxeUXE&h=AT2LjSXF6ZzJvaac4RmlIwgQruVE-qPT0wpBuE7Q1T-s7Tqaj_AmodwRwZweDemn6AtptxPaUpvue0xspYptzbs5lnarU3NaAwjwR8Xc9TOJHl4WbVtHDGth9boKXfDIl5inGKC71jU" 
        target="_blank" rel="noopener noreferrer" class="btn btn-link"> Privacy Policy </a>
      <v-toolbar id="iconBar" flat dark>
          <v-btn flat clickable color="white" @click="fb()">
              <span>FACEBOOK</span>
          </v-btn>
          <v-btn flat clickable color="white" @click="insta()">
              <span>INSTAGRAM</span>
          </v-btn>
          <v-btn flat clickable color="white" @click="linkin()">
              <span>LINKEDIN</span>
          </v-btn>
          <v-btn flat clickable color="white" @click="union()">
              <span>UNION SITE</span>
          </v-btn>
      </v-toolbar>


    </div>
  </div>

</template>

<script>

  export default {
    methods: {
      fb() {
        window.location.href = "https://www.facebook.com/ICSquash/";
      },
      insta() {
        window.location.href = "https://www.instagram.com/icsquash/?hl=en";
      },
      linkin() {
        window.location.href = "https://www.linkedin.com/groups/10407996/";
      },
      union() {
        window.location.href = "https://www.imperialcollegeunion.org/activities/a-to-z/squash";
      }
    }

  }

</script>

<style>

  #iconBar {
    width: 500px
  }

  .v-btn {
    min-width: 0px;
  }

  .v-toolbar__content {
    padding-left: 0px;
  }

  .main {
    width:100%;
  }

  #ICemail {
    font-size: 20px;
    height: 24px;
  }

  #footerLogo {
    max-height: 55px;
    height: auto;
    width:auto;
    float: right;
    margin: 15px

  }

  #footer {
    width: 100%;
    color: white;
    background-color: rgba(0,0,0,0.87);
  }

</style>
