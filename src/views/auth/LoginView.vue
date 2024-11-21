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
    <v-responsive class="border rounded">
      <v-app :theme="theme" class="transparent-app">
        <v-app-bar class="px-3">
          <v-spacer></v-spacer>

          <v-btn
            :prepend-icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'"
            text="Toggle Theme"
            slim
            @click="onClick"
          ></v-btn>
        </v-app-bar>

        <v-main>
          <v-container class="transparent-container">
            <v-row class="">
              <v-col cols="12" md="6"
                >Lorem ipsum dolor sit amet consectetur adipisicing elit. Similique eligendi,
                quibusdam ab maiores perspiciatis quasi eveniet fuga facilis repellat? Quibusdam
                necessitatibus blanditiis labore nisi, mollitia cupiditate in porro ea eveniet?
              </v-col>
              <v-divider vertical></v-divider>
              <v-col cols="12" md="6" class="d-flex justify-center align-center">
                <v-card class="glassmorphic-card" elevation="16" max-width="800">
                  <template v-slot:title>
                    <span class="text-center d-block font-weight-white">LOGIN</span>
                  </template>

                  <v-card-text class="pt-4">
                    <v-form fast-fail @submit.prevent>
                      <v-text-field label="Email" variant="outlined">
                        <template v-slot:label>
                          <v-icon class="mr-1">mdi-email</v-icon> Email
                        </template>
                      </v-text-field>

                      <v-text-field label="Password" type="password" variant="outlined">
                        <template v-slot:label>
                          <v-icon class="mr-1">mdi-lock</v-icon> Password
                        </template>
                      </v-text-field>

                      <v-btn class="mt-2 rounded bg-primary" type="submit" block>Login</v-btn>
                    </v-form>
                    <v-divider class="my-5"></v-divider>
                    <h5 class="text-center">
                      Don't have account?
                      <RouterLink class="text-white" to="/signUp"><b>Sign up</b></RouterLink>
                    </h5>
                  </v-card-text>
                </v-card></v-col
              >
            </v-row>
          </v-container>
        </v-main>

        <v-footer border app>2024-Copyright TaskHub</v-footer>
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
