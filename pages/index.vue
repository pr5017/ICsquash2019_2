<template>
  <div>
    <v-layout row mx0 px0 >
      <v-carousel
        id="featuredphotos"
        v-if="$vuetify.breakpoint.mdAndDown"
        :height="featuredphotos"
        hide-delimiters
      >
        <v-carousel-item v-for="(item,i) in items" :key="i" :src="item.src"></v-carousel-item>
      </v-carousel>
      <v-btn
        id="join_us"
        round
        small
        color="beige lighten-3"
        absolute
        @click="dialog = !dialog"
        href="/join_us"
        target="_blank"
      >Join Us</v-btn>
      <v-img :src="bg_lg_index" v-if="$vuetify.breakpoint.lgAndUp" width="100vw" height="100vh"></v-img>
    </v-layout>
    <v-layout row wrap id="menu" text-xs-center clickable>
      <v-flex class="menu-btn stage" xs12>
        <div class="fill-height main-fab mx-auto ball " @click="book_courts()" id="btn-bookCourt">
          <span class="shadow"></span>
          Book Courts
        </div>
      </v-flex>
      <v-flex class="menu-btn stage" xs12 lg6>
        <div class="fill-height main-fab ball" @click="gallery()" id="btn-gallery">
          <span class="shadow"></span>
          Gallery
        </div>
      </v-flex>
      <v-flex xs6 lg6 class="menu-btn stage">
        <div class="fill-height main-fab ball" @click="contacts()" id="btn-contacts">
          <span class="shadow"></span>
          Contacts
        </div>
      </v-flex>
      <v-flex xs6 lg6 class="menu-btn stage">
        <div class="fill-height main-fab ball" @click="about_us()" id="btn-aboutUs">
          <span class="shadow"></span>
          About Us
        </div>
      </v-flex>
      <v-hover v-slot:default="{ hover }">
        <v-flex xs12 lg6 class="menu-btn stage">
          <div class="fill-height main-fab ball" @click="shop()" id="btn-shop">
            <span class="shadow"></span>
            Shop
          </div>
        </v-flex>
      </v-hover>
    </v-layout>
    <!-- <v-layout>
          <v-flex lg12 offset-lg2>
             <v-btn fab align="center">Book Courts</v-btn>
             </v-flex> 
          <v-flex lg3 offset-lg1 color="indigo">
             <v-btn fab align="right">Gallery</v-btn>
             </v-flex>
          <v-flex lg3 offset-lg3>
             <v-btn fab align="left">Contacts</v-btn>
             </v-flex>
    </v-layout>-->
  </div>
</template>

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

#btn-bookCourt {
  background-color: #1e88e5;
  font-family: monospace;
}

#btn-gallery {
  background-color: #64b5f6;
  font-family: monospace;
}

#btn-contacts {
  background-color: #90caf9;
  font-family: monospace;
}

#btn-aboutUs {
  background-color: #bbdefb;
  font-family: monospace;
}

#btn-shop {
  background-color: #e3f2fd;
  font-family: monospace;
}

.menu-btn {
  height: 25%;
  line-height: 200%;
  font-size: 35px;
  font-weight: 400;

  /deep/ .div {
    height: 100%;
  }
}

#menu {
  height: calc(100vh - 277px);
  margin: 0 !important;
}

.clickable {
  cursor: pointer;
}

/* Small devices (portrait tablets and large phones, 600px and up) */
@media only screen and (min-width: 600px) {
  #featuredphotos {
    height: 1000px;
  }

  .menu-btn {
    line-height: 100px;
  }

  #join_us {
    font-size: 25px;
    top: 410px;
  }

  #menu {
    height: 375px;
  }
}

/* Medium devices (landscape tablets, 768px and up) */
@media only screen and (min-width: 768px) {
  #join_us {
    font-size: 30px;
    top: 410px;
  }

  #menu {
    height: 600px;
  }
}

/* sub class Med-Large */
@media only screen and (min-width: 960px) {
  #join_us {
    font-size: 30px;
    top: 710px;
  }
}

/* Large devices (laptops/desktops, 1280px and up) */
@media only screen and (min-width: 1280px) {
  .my-btn {
    color: white;
    background-color: black;
    
  }

  #btn-bookCourt {
    @extend .my-btn;
    font-weight: 400;
    font-size: 24px;
  }

  #btn-gallery {
    @extend .my-btn;
    font-weight: 600;
  }

  #btn-contacts {
    @extend .my-btn;
    font-weight: 600;
  }

  #btn-aboutUs {
    @extend .my-btn;
    font-weight: 800;
    float: left;
    margin-left:10px;
  }

  #btn-shop {
    @extend .my-btn;
    font-weight: 800;
    float: right;
    margin-right:10px;
  }

  // squash ball
  .ball {
    display: inline-block;
    width: 100%;
    height: 100%;
    // margin: 0;
    border-radius: 50%;
    position: relative;
    background: url(../assets/squash-ball-01.svg) no-repeat;
    background-size: 100%;
  }

  .ball:before {
    content: '';
    position: absolute;
    top: 1%;
    left: 5%;
    width: 90%;
    height: 90%;
    border-radius: 50%;
    background: radial-gradient(circle at 50% 0px, #ffffff, rgba(255, 255, 255, 0) 58%);
    -webkit-filter: blur(5px);
    z-index: 2;
  }

  // }
  .ball .shadow {
    position: absolute;
    width: 100%;
    height: 85px;
    background: radial-gradient(circle, rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.1) 40%, rgba(0, 0, 0, 0) 50%);
    -webkit-transform: rotateX(90deg) translateZ(-160px);
    transform: rotateX(90deg) translatex(-20px) translatez(-160px);
    z-index: 1;
  }

  .stage {
    width: 100vw;
    // height: 100vh;
    display: inline-block;
    // margin: 0px;
    -webkit-perspective: 1200px;
    -moz-perspective: 1200px;
    -ms-perspective: 1200px;
    -o-perspective: 1200px;
    perspective: 1200px;
    -webkit-perspective-origin: 50% 50%;
    -moz-perspective-origin: 50% 50%;
    -ms-perspective-origin: 50% 50%;
    -o-perspective-origin: 50% 50%;
    perspective-origin: 50% 50%;
  }

  // end squash ball
  #join_us {
    font-size: 30px;
    top: 90vh;
    z-index: 200;
  }

  .menu-btn {
    font-size: 27px;
    line-height: 200px;
    
    
  }

  .main-fab {
    border-radius: 50%;
    width: 200px;
    height: 200px;

    &:hover {
      // box-shadow: 1px 10px 10px 1px grey;
      transition: all 1.5s;
      transform: translateY(-75px);
    }

    &:active {
      box-shadow: 1px 10px 10px 8px grey;
    }
  }

  #menu {
    position: absolute;
    top: 0px;
    bottom: 200px;
    padding: 0 20px;
    min-width: 100%;
    min-height: 768px;
    max-height: 768px;
    padding-top: 200px;
    padding-left: 0px;
    overflow: visible;
  }
}
</style>


<script>
var clubformalPath = require("../assets/Squash-Club-Formal-2019 3.jpg");
var clubcasualPath = require("../assets/52969833_2383404548358784_5845434748800860160_o.jpg");
var logoPath = require("../assets/Logo.jpg");
var pauline = require("../assets/IMG_5963.jpg");
export default {
  data() {
    return {
      featuredphotos: "277px",
      screenSize: "",
      bg_lg_index: require("../assets/squash-court-2.jpg"),

      items: [
        {
          src: clubformalPath
        },
        {
          src: clubcasualPath
        },
        {
          src: logoPath
        },
        {
          src: pauline
        }
      ],
      screenHeight: ""
    };
  },
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
    book_courts() {
      window.location.href = "/book_courts";
    },
    gallery() {
      window.location.href = "/gallery";
    },
    contacts() {
      window.location.href = "https://www.facebook.com/ICSquash/";
    },
    about_us() {
      window.location.href = "/about_us";
    },
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
