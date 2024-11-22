<script setup>
import { ref } from 'vue'
import BackgroundLayout from '@/components/auth/BackgroundLayout.vue'

const theme = ref('light')

function onClick() {
  theme.value = theme.value === 'light' ? 'dark' : 'light'
}
</script>

<template>
  <BackgroundLayout>
    <v-responsive>
      <v-app :theme="theme" class="transparent-app">
        <!--<v-app-bar class="px-3" color="transparent">
          <v-spacer></v-spacer>

          <v-btn
            :prepend-icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'"
            slim
            @click="onClick"
          ></v-btn>
        </v-app-bar>-->

        <v-main>
          <v-container class="transparent-container">
            <v-row class="">
              <v-col cols="12" md="6">
                <h4 class="text-white justify-content-center pt-16">
                  A Task Manager app helps users create tasks, assign priorities, and monitor
                  progress to stay organized and meet deadlines efficiently.
                </h4>
              </v-col>
              <v-divider vertical></v-divider>
              <v-col cols="12" md="6" class="d-flex justify-center align-center">
                <v-card class="glassmorphic-card" elevation="16" max-width="800">
                  <template v-slot:title>
                    <span class="text-center d-block font-weight-white"><h2>SIGN UP</h2></span>
                  </template>

                  <v-card-text class="pt-4">
                    <v-form fast-fail @submit.prevent>
                      <v-text-field
                        label="First name"
                        variant="outlined"
                        class="text-end"
                      ></v-text-field>
                      <v-text-field label="Last name" variant="outlined"></v-text-field>
                      <v-text-field label="Email" variant="outlined"></v-text-field>

                      <v-text-field label="Password" type="password" variant="outlined">
                      </v-text-field>
                      <v-text-field label="Confirm Password" type="password" variant="outlined">
                      </v-text-field>

                      <v-btn class="mt-2 rounded" color="secondary" type="submit" block
                        >Sign up</v-btn
                      >
                    </v-form>
                    <v-divider class="my-5"></v-divider>
                    <h4 class="text-center">
                      Already have an account?
                      <RouterLink class="text-white" to="/login"><b>Login</b></RouterLink>
                    </h4>
                  </v-card-text>
                </v-card></v-col
              >
            </v-row>
          </v-container>
        </v-main>

        <!-- <v-footer border app>2024-Copyright TaskHub</v-footer> -->
      </v-app>
    </v-responsive>
  </BackgroundLayout>
</template>

<style scoped>
.transparent-app {
  background: transparent;
}
.glassmorphic-card {
  color: white;
  background: rgba(64, 64, 64, 0.15); /* Transparent white */
  backdrop-filter: blur(25px); /* Frosted glass effect */
  -webkit-backdrop-filter: blur(10px); /* Safari support */
  border: 2px solid rgba(255, 255, 255, 0.826); /* Frosted border */
  border-radius: 16px; /* Rounded corners */
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* Shadow for depth */
  padding: 20px; /* Optional padding for inner spacing */
  width: 70%;
}
.v-divider {
  background-color: rgba(246, 240, 240, 0.15);
  width: 2px;
}
</style>
