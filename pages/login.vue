<!-- eslint-disable vue/attributes-order -->
<template>
  <div class="ma-5">
    <v-card width="400" class="mx-auto mt-16 pb-10">
      <div align="center" class="pt-5 font-weight-black text-h5">Login</div>
      <v-card-text>
        <v-row>
          <v-col cols="12" md="12">
            <v-text-field
              label="User"
              prepend-inner-icon="mdi-account"
              outlined
              dense
              hide-details="auto"
            />
          </v-col>
          <v-col cols="12" md="12">
            <v-text-field
              label="Password"
              prepend-inner-icon="mdi-lock"
              outlined
              dense
              hide-details="auto"
              :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
              :type="show1 ? 'text' : 'password'"
              @click:append="show1 = !show1"
            />
          </v-col>
        </v-row>
      </v-card-text>
      <v-card-actions>
        <v-spacer />
        <v-btn @click="secess" color="info" class="mt-5" block rounded
          >Login</v-btn
        >
        <v-spacer />
      </v-card-actions>
      <div class="mt-3 text-center">
        <div>Not a member?</div>
        <v-btn text to="/register"><div class="blue--text">Signup</div></v-btn>
      </div>
    </v-card>
  </div>
</template>

<script>
export default {
  layout: 'blank',
  data() {
    return {
      show1: false,
      show2: true,
      password: null,
    }
  },
  methods: {
    secess() {
      this.$toast.success('Login Sucessfully', {
        duration: 1000,
        position: 'top-center',
        theme: 'bubble',
      })
    },
  },
}
</script>
