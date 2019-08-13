<template>
  <form class="form" ref="form">
    <v-toolbar
      absolute
      color="teal lighten-3"
      dark
      flat
      scroll-off-screen
      scroll-target="#scrolling-techniques"
    >
      <v-toolbar-title id="title">Registration Form</v-toolbar-title>
    </v-toolbar>

    <v-text-field
      v-model="name"
      v-validate="'required|max:10'"
      :counter="10"
      :error-messages="errors.collect('name')"
      label="Name"
      data-vv-name="name"
      required
    ></v-text-field>
    <v-text-field
      v-model="surname"
      v-validate="'required|max:20'"
      :counter="20"
      :error-messages="errors.collect('surname')"
      label="Surname"
      data-vv-name="surname"
      required
    ></v-text-field>
    <v-text-field
      v-model="email"
      v-validate="'required|email'"
      :error-messages="errors.collect('email')"
      label="E-mail"
      data-vv-name="email"
      required
    ></v-text-field>
    <v-select
      v-model="student_status"
      v-validate="'required'"
      :items="items"
      :error-messages="errors.collect('select')"
      label="Student status"
      data-vv-name="select"
      required
    ></v-select>

    <v-checkbox
      v-model="checkbox"
      hide-details
      value="1"
      label="Team Trial"
      data-vv-name="checkbox"
      type="checkbox"
    ></v-checkbox>
    <v-select :disabled="!checkbox" v-model="trial_time" label="Trial Time" :items="trial_times"></v-select>

    <v-flex sm6 left>
      <!--DIALOG  -->
      <div class="text-center">
        <v-dialog v-model="dialog" width="500">
          <template v-slot:activator="{ on }">
            <v-btn color="teal lighten-2" @click="submit()" >submit</v-btn>
          </template>

          <v-card>
            <v-card-title class="headline grey lighten-2" primary-title>Submission Complete!</v-card-title>

            <v-card-text>หิวข้าวจัง</v-card-text>

            <v-divider></v-divider>

            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn color="primary" text @click="popUpDown()">OK</v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>
      </div>
      <!-- END DIALOG -->
    </v-flex>

    <v-flex sm6 right>
      <v-btn :ripple="{class: 'red--text'}" color="grey lighten-2" @click="clear">clear</v-btn>
    </v-flex>
  </form>
</template>


<style>
.form {
  margin: 20px;
  font-size: 12px;
  /* column-count: 2; */
  padding-top: 64px;
  max-width: 500;
}

#title {
  font-size: 20px;
  font-weight: 1000;
}
</style>



<script>
import Vue from "vue";
import VeeValidate from "vee-validate";

Vue.use(VeeValidate);

export default {
  $_veeValidate: {
    validator: "new"
  },

  data: () => ({
    name: "",
    surname: "",
    email: "",
    student_status: null,
    items: ["student", "alumni"],
    checkbox: null,
    enabled: false,
    trial_time: "9.00-10.00",
    dictionary: {
      attributes: {
        email: "E-mail Address"
        // custom attributes
      },
      custom: {
        name: {
          required: () => "Name cannot be empty",
          max: "The name field may not be greater than 10 characters"
          // custom messages
        },
        surname: {
          required: () => "Surname can not be empty",
          max: "The name field may not be greater than 20 characters"
          // custom messages
        },
        student_status: {
          required: "Select field is required"
        }
      }
    },
    trial_times: ["9.00-10.00", "10.00-11.00", "12.00-13.00"],
    dialog: false
  }),

  mounted() {
    this.$validator.localize("en", this.dictionary);
  },

  methods: {
    submit() {
      console.log(
        this.name,
        this.surname,
        this.email,
        this.student_status,
        this.checkbox,
        this.trial_time
      );
      this.$validator.validateAll().then((v)=>{
        if(v)this.dialog=true;
        
        
      })
      
      // this.dialog = true;
    },
    clear() {
      this.name = "";
      this.surname = "";
      this.email = "";
      this.studentstatus = null;
      this.checkbox = null;
      this.$validator.reset();
    },
    popUpDown() {
      this.dialog = false;
      window.location.href= '/';
    }
  }
};
</script>