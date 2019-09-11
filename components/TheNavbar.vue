<template>
  <nav class="nav">
    <div>
      <v-toolbar flat dark>
        <v-btn flat clickable color="white" @click="home()">
            <span>IC SQUASH</span>
        </v-btn>
        <v-spacer></v-spacer>
        <v-btn flat clickable color="white" @click="book_courts()">
            <span>BOOK COURTS</span>
        </v-btn>
        <v-btn flat clickable color="white" @click="login()">
            <span>LOGIN</span>
            <v-icon right>exit_to_app</v-icon>
        </v-btn>
      </v-toolbar>
    </div>
  </nav>
</template>

<script>
  export default {
    methods: {
      home() {
        window.location.href = "/";
      },
      book_courts() {
        window.location.href = "/book_courts";
      }
    }
  }
</script>

<style>

  #home {
    color: white;

  }

  .clickable {
    cursor: pointer;
  }

</style>
