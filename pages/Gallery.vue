<template>
  <v-container fluid grid-list-sm id="layout">
    <h1 align="center">Gallery</h1>
    <v-layout wrap>
      <v-flex d-flex>
        <v-layout column>
          <v-flex d-flex>
            <v-hover v-slot:default="{ hover }">
              <v-card :elevation="hover ? 12 : 2" :class="{ 'on-hover': hover }">
                <v-img :src="pauline1" class="image">
                  <!-- start carousel -->
                  <v-card-title
                    v-if="hover"
                    class="d-flex v-card--reveal font_size white--text clickable"
                    @click="album1 = true"
                  >Double Tournament</v-card-title>

                  <!-- carousel nactivator -->
                  <v-dialog v-model="album1">
                    <v-card>
                      <!-- carousel -->
                        <v-carousel>
                           <v-carousel-item v-for="(photo,i) in album1_photos" :key="i" :src="photo.src"></v-carousel-item>
                        </v-carousel>
                    </v-card>
                  </v-dialog>
        <!-- END popup_carousel -->
                </v-img>
              </v-card>
            </v-hover>
          </v-flex>
          <v-flex d-flex>
            <v-hover v-slot:default="{ hover }">
              <v-card :elevation="hover ? 12 : 2" :class="{ 'on-hover': hover }">
                <v-img :src="pauline2" class="image">
                  <!-- start carousel2 -->
                  
                  <v-card-title
                    v-if="hover"
                    class="d-flex v-card--reveal font_size white--text clickable"
                    
                    @click="album2 = true"
                  >Trip</v-card-title>

                  <!-- carousel nactivator -->
                  <v-dialog v-model="album2">
                    <v-card>
                      <!-- carousel -->
                        <v-carousel >
                           <v-carousel-item v-for="(photo,i) in album2_photos" :key="i" :src="photo.src"></v-carousel-item>
                        </v-carousel>
                    </v-card>
                  </v-dialog>
       
                  <!-- end carousel2 -->
                </v-img>
              </v-card>
            </v-hover>
          </v-flex>
        </v-layout>
      </v-flex>

      <v-flex d-flex>
        <v-hover v-slot:default="{ hover }">
          <v-card :elevation="hover ? 12 : 2" :class="{ 'on-hover': hover }">
            <v-img :src="pauline3" class="image">
              <!-- start carousel3 -->
          
                  <v-card-title
                    v-if="hover"
                    class="d-flex v-card--reveal font_size white--text clickable"
                    @click="album3 = true"
                  >Photoshoot</v-card-title>

                  <!-- carousel nactivator -->
                  <v-dialog v-model="album3">
                    <v-card>
                      <!-- carousel -->
                        <v-carousel>
                          <v-carousel-item v-for="(photo,i) in album3_photos" :key="i" :src="photo.src"></v-carousel-item>
                        </v-carousel>
                    </v-card>
                  </v-dialog>
        
              <!-- end carousel3 -->
            </v-img>
          </v-card>
        </v-hover>
      </v-flex>
    </v-layout>

    <v-layout wrap>
      <v-flex d-flex>
        <v-hover v-slot:default="{ hover }">
          <v-card :elevation="hover ? 12 : 2" :class="{ 'on-hover': hover }">
            <v-img :src="pauline4" class="image">
               <!-- start carousel4 -->
          
                  <v-card-title
                    v-if="hover"
                    class="d-flex v-card--reveal font_size white--text clickable"
                    
                    @click="album4 = true"
                  >Promo</v-card-title>

                  <!-- carousel nactivator -->
                  <v-dialog v-model="album4">
                    <v-card>
                      <!-- carousel -->
                        <v-carousel>
                          <v-carousel-item v-for="(photo,i) in album4_photos" :key="i" :src="photo.src"></v-carousel-item>
                        </v-carousel>
                    </v-card>
                  </v-dialog>
        
              <!-- end carousel4 -->
            </v-img>
          </v-card>
        </v-hover>
      </v-flex>
      <v-flex d-flex>
        <v-hover v-slot:default="{ hover }">
          <v-card :elevation="hover ? 12 : 2" :class="{ 'on-hover': hover }">
            <v-img :src="pauline5" class="image">
                <!-- start carousel5 -->
          
                  <v-card-title
                    v-if="hover"
                    class="d-flex v-card--reveal font_size white--text clickable"
                    
                    @click="album5 = true"
                  >Pauline!</v-card-title>

                  <!-- carousel nactivator -->
                  <v-dialog v-model="album5">
                    <v-card >
                      <!-- carousel -->
                        <v-carousel>
                         <v-carousel-item v-for="(photo,i) in album5_photos" :key="i" :src="photo.src" ></v-carousel-item>
                        </v-carousel>
                    </v-card>
                  </v-dialog>
        
              <!-- end carousel5 -->
            </v-img>
          </v-card>
        </v-hover>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<style>
.image {
  height: 100%;
  width: 100%;
}

.v-card {
  transition: opacity 0.7s;
}

.v-card.on-hover {
  opacity: 0.7;
}
.font_size {
  font-family: monospace;
  font-size: 42px;
  font-weight: 800;
  text-shadow: 1px 1px black;
}
.v-card--reveal {
  justify-content: center;
  width: 100%;
  height: 100%;
}

h1 {
  font-family: sans-serif;
  font-size: 60px;
  font-weight: 100;
  font-style: italic;
  padding: 30px auto;
}

.clickable {
  cursor: pointer;
}
.card_carousel{
  align-self: auto;
}
.v-dialog{
  height:500px;
  width:800px;
}

/* Medium devices (landscape tablets, 768px and up) */
@media only screen and (min-width: 768px) {
  h1 {
    font-size: 80px;
  }
  .v-card {
    margin: 5px;
  }
  #layout {
    padding: 50px 80px 0 80px;
  }
}
/* Large devices (laptops/desktops, 1280px and up) */
@media only screen and (min-width: 1280px) {
  .font_size {
    font-size: 80px;
  }
  h1 {
    font-size: 100px;
  }
  #layout {
    padding: 50px 120px 0 120px;
  }
}
</style>






<script>
// picture for carousel
var clubformalPath = require("../assets/Squash-Club-Formal-2019 3.jpg");
var clubcasualPath = require("../assets/52969833_2383404548358784_5845434748800860160_o.jpg");
var logoPath = require("../assets/Logo.jpg");
var pauline = require("../assets/IMG_5963.jpg");
// picture for carousel

export default {
  data: () => ({
    pauline1: require("../assets/236ea0d1-f335-4e4b-9564-7a55c82ae125.jpg"),
    pauline2: require("../assets/IMG_5963.jpg"),
    pauline3: require("../assets/IMG_7890.JPG"),
    pauline4: require("../assets/91DC1719-F2AE-467F-902A-2F5B2C1065D2.JPG"),
    pauline5: require("../assets/IMG_8800.JPG"),
   
    album1:false,
    album1_photos: [
      {
        src:pauline
      },
      {
        src: clubformalPath
      },
    ],

    album2:false,
    album2_photos: [
      {
        src:pauline
      },
      
    ],

    album3:false,
    album3_photos: [
      {
        src:pauline
      },
      {
        src:pauline
      },
    ],

    album4: false,
    album4_photos: [
      {
        src:pauline
      },
      {
        src:pauline
      },
    ],

    album5: false,
    album5_photos: [
      {
        src:pauline
      },
      {
        src:pauline
      },
    ],
    
  }),

  methods: {
    
  }
};
</script>