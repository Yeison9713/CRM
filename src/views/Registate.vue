<template>
  <v-parallax
    dark
    src="https://martechtoday.com/wp-content/uploads/2018/08/crm-concept-table-charts-ss-1920_cjnnna.jpg"
    style="height: 100%; width: 100%;"
  >
    <v-container class="lighten-5">
      <v-row align="center" justify="space-around">
        <v-col class="center" cols="12" sm="4">
          <v-card>
            <v-card-title class="center">
              <v-icon large left>mdi-cards</v-icon>
              <span class="title font-weight-light">Registrarse con</span>
              <div class="text-center">
                <v-btn color="blue" class="ma-1 white--text" fab>
                  <v-icon dark>mdi-facebook</v-icon>
                </v-btn>
                <v-btn color="blue" class="ma-1 white--text" fab>
                  <v-icon dark>mdi-google</v-icon>
                </v-btn>
              </div>
              <!-- <v-col cols="12">
                  <span>-------- or ---------------</span>
              </v-col> -->
            </v-card-title>
            <v-form ref="form" v-model="valid" lazy-validation>
              <v-col class="center" cols="12">
                <v-text-field v-model="name" :rules="nameRules" label="Usuario" outlined required>
                  <v-icon slot="append" color="black">mdi-account</v-icon>
                </v-text-field>
                <v-text-field
                  v-model="password"
                  :rules="passwordRules"
                  label="Password"
                  outlined
                  required
                >
                  <v-icon slot="append" color="black">mdi-eye</v-icon>
                </v-text-field>
                <v-text-field label="Repet Password" outlined required>
                  <v-icon slot="append" color="black">mdi-eye</v-icon>
                </v-text-field>
                <router-link to="/">
                  <v-btn color="success" block class="ma-1" @click="validate">Ingresar</v-btn>
                </router-link>
                <v-btn class="ma-1" block outlined color="red">registrase</v-btn>
              </v-col>
            </v-form>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-parallax>
</template>
<style>
.v-parallax__image-container img {
  transform: rotate3d(1, 1, 1, 35deg) !important;
  height: 80%;
  width: 50%;
}

.v-card__title {
  justify-content: center;
}

.v-input__control {
  width: 100% !important;
}

.v-input--checkbox .v-input__control .v-input__slot {
  width: 100%;
}

.v-input--checkbox .v-input__control label {
  width: 100%;
  display: flex;
  justify-content: space-between;
}
</style>

<script>
export default {
  data: () => ({
    valid: true,
    name: "",
    nameRules: [v => !!v || "User is required"],
    password: "",
    passwordRules: [v => !!v || "Password is required"],
    checkbox: false
  }),

  methods: {
    validate() {
      if (this.$refs.form.validate()) {
        this.snackbar = true;
      }
    }
  }
};
</script>