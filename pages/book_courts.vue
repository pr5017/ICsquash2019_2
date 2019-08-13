<template>
  <v-container fluid> 
    <v-layout column wrap>
      <v-flex>
        <v-header bold id="a1">Book Court</v-header>
        <v-subheader v-text="'Pick a date you would like to book'"></v-subheader>
      </v-flex>
      <!-- date picker -->
      <template>
        <v-layout>
          <v-date-picker v-model="picker" mb-2 :type="month ? 'month' : 'date'" functionEvents="null" ></v-date-picker>
        </v-layout>
      </template>
      <!-- date picker -->

      <v-flex>
        <v-subheader v-text="'Maximum of 2 time slots can be selected'"></v-subheader>
      </v-flex>

      <v-flex>
        <v-select v-model="t1" :items="times" label="Select" multiple chips @input="limiter" class="select"></v-select>
      </v-flex>

        <!--DIALOG  -->
      <div class="text-center">
        <v-dialog v-model="dialog_book" width="500">
          <template v-slot:activator="{on}">
              <v-btn @click="submit_booking()" class="btn">BOOK</v-btn>
          </template>

          <v-card>
            <v-card-title class="headline grey lighten-2" primary-title>booking accepted!</v-card-title>

            <v-card-text>Court reserved for {{this.picker}} from {{this.t1}}</v-card-text>

            <v-divider></v-divider>

            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn color="primary" text @click="popUpDown()">OK</v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>
      </div>
      <!-- END DIALOG -->
      <v-btn @click="backHome()" class="btn">BACK</v-btn>
    </v-layout>
  </v-container>
</template>

<style>
.v-container{
  margin: auto 100px;
}
#a1{
    font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
    font-size: 50px;
    
}
.select{
    width: 300px;
}
.btn {
    width: 20px;
}
</style>

<script>
export default {
  data() {
    return {
      t1: [],
      picker: new Date().toISOString().substr(0, 10),
      times: ["7.00-7.45", "7.45-8.30", "8.30-9.15", "9.15-10.00"],
      dialog_book:false,
      
    };
  },

//event//
computed: {
      functionEvents () {
        return this.month ? this.monthFunctionEvents : this.dateFunctionEvents
      },
    },
//event//
  methods: {
    backHome() {
      window.location.href = "/";
    },
    submit_booking() {
      console.log(this.picker, this.t1);
      this.dialog_book= true;
    },
    popUpDown() {
      this.dialog_book= false;
      
    },
    limiter(e) {
      if (e.length > 2) {
        console.log("maximum2,e");
        e.pop();
      }
    },
    
    // event//
    dateFunctionEvents (date) {
        const [,, day] = date.split('-')
        if ([12, 17, 28].includes(parseInt(day, 10))) return true
        if ([1, 19, 22].includes(parseInt(day, 10))) return ['red', '#00f']
        return false
      },
      monthFunctionEvents (date) {
        const month = parseInt(date.split('-')[1], 10)
        if ([1, 3, 7].includes(month)) return true
        if ([2, 5, 12].includes(month)) return ['error', 'purple', 'rgba(0, 128, 0, 0.5)']
        return false
      },
    // event//
  }
};
</script>






   


