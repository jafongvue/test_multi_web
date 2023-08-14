<template>
    <div class="ma-5">
      <v-card max-width="450" class="mx-auto">
        <div align="center" class="pa-5 font-weight-black text-h5">Register</div>
        <v-divider />
        <v-card-text>
          <v-row>
            <v-col cols="12" md="6">
              <v-text-field label="name" outlined dense hide-details="auto" />
            </v-col>
            <v-col cols="12" md="6">
              <v-text-field label="lastname" outlined dense hide-details="auto" />
            </v-col>
            <v-col cols="12">
              <v-text-field label="Phonenumber" outlined dense hide-details="auto" />
            </v-col>
            <v-col cols="12">
              <v-text-field label="Email" outlined dense hide-details="auto" />
            </v-col>
            <v-col cols="12" md="4">
              <v-text-field label="MM" outlined dense hide-details="auto" />
            </v-col>
            <v-col cols="12" md="4">
              <v-text-field label="YY" outlined dense hide-details="auto" />
            </v-col>
            <v-col cols="12" md="4">
              <v-text-field label="Code" outlined dense hide-details="auto" />
            </v-col>
            <v-col cols="12">
              <v-text-field
                label="Password"
                outlined
                dense
                hide-details="auto"
                :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                :type="show1 ? 'text' : 'password'"
                @click:append="show1 = !show1"
              />
            </v-col>
            <v-col cols="12">
              <v-text-field
                label="Comfirm Password"
                outlined
                dense
                hide-details="auto"
                :append-icon="show3 ? 'mdi-eye' : 'mdi-eye-off'"
                :type="show3 ? 'text' : 'password'"
                @click:append="show3 = !show3"
              />
            </v-col>
            <v-col cols="12">
              <v-btn block color="info" to="/login"> Submit </v-btn>
            </v-col>
            <v-col>
              <div
                class="text-decoration-underline text-center"
                @click="$router.go(-1)"
              >
                Back
              </div>
            </v-col>
          </v-row>
        </v-card-text>
      </v-card>
    </div>
  </template>
  <script>
  export default {
    layout: "blank",
    data() {
      return {
        show1: false,
        show2: true,
        show3: false,
        show4: true,
        password: null,
      };
    },
  };
  </script>
  