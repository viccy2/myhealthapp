<template>
  <v-container fluid class="login-container">
    <v-row justify="center">
      <v-col cols="12" sm="8" md="4">
        <v-card
          class="pa-6 transparent-card"
          elevation="0"
          outlined
          shaped
          style="margin-top:80px;height:500px;"
        >
          <v-img
            src="https://www.gstatic.com/mobilesdk/160505_mobilesdk/logo/2x/firebase_28dp.png"
            max-height="50"
            class="mx-auto"
          ></v-img><br>
          <p class="text-center" style="font-size:17px;text-align:center;"> ENTER YOUR DETAILS BELOW TO SIGN IN. </p>
          <br><v-card-text>
            <v-form @submit.prevent="login">
              <v-text-field
                v-model="email"
                label="Email"
                outlined
                prepend-icon="mdi-account-outline"
                required
              ></v-text-field><br>
              <v-text-field
                v-model="password"
                label="Password"
                type="password"
                outlined
                prepend-icon="mdi-lock-outline"
                required
              ></v-text-field><br><br>
              <v-btn
                color="primary"
                class="white--text"
                :loading="loading"
                :disabled="loading"
                type="submit"
                block
              >
                <template v-if="!loading">
                  Sign in
                </template>
                <template v-else>
                  <v-progress-circular
                    indeterminate
                    color="white"
                    size="22"
                  ></v-progress-circular>
                </template>
              </v-btn>
            </v-form>
          </v-card-text><br>
          
          <p>
            
            <router-link to="/" class="primary--text">
              <center>
                <v-btn text color="primary" style="font-size:12px;text-align:center;">
                   don't have account? create new account
                </v-btn>
                </center>
            </router-link><br>
            <!-- <v-btn text color="primary">Forgot password?</v-btn> -->
          </p><br><br>
            
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      loading: false,
      email: '',
      password: ''
    };
  },
  methods: {
    login() {
      // Simulating login process
      this.loading = true;
      setTimeout(() => {
        // Simulating successful login after 2 seconds
        console.log('Login successful');
        this.loading = false;
      }, 2000);
    }
  }
};
</script>

<style scoped>
.login-container {
  background-color: rgba(255, 255, 255, 0.5);
  height:100%; /* Set background color */
}

.transparent-card {
  background-color: #ffffff; /* Make the card background white */
}

.v-card__actions {
  background-color: #ffffff; /* Match card background */
}

.custom-button {
  /* Add any custom styling to the button */
  border-radius: 25px;
  text-transform: uppercase;
}
</style>
