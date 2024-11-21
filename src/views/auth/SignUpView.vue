<script>
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
      <v-app :theme="theme" class="app-background">
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
          <v-container>
            <v-row>
              <v-col
                >Lorem ipsum dolor sit amet consectetur adipisicing elit. Similique eligendi,
                quibusdam ab maiores perspiciatis quasi eveniet fuga facilis repellat? Quibusdam
                necessitatibus blanditiis labore nisi, mollitia cupiditate in porro ea eveniet?
              </v-col>
              <v-col cols="12" md="6" class="mx-auto">
                <v-card
                  class="mx-auto"
                  prepend-icon="$vuetify"
                  subtitle="The #1 Vue UI Library"
                  elevation="16"
                  max-width="344"
                >
                  <template v-slot:title>
                    <span class="font-weight-black">Welcome to Vuetify</span>
                  </template>

                  <v-card-text class="bg-surface-light pt-4">
                    <v-form fast-fail @submit.prevent>
                      <v-text-field label="Firstname" variant="outlined"></v-text-field>
                      <v-text-field label="Lastname" variant="outlined"></v-text-field>
                      <v-text-field label="Email" variant="outlined"></v-text-field>

                      <v-text-field
                        label="Password"
                        type="password"
                        variant="outlined"
                      ></v-text-field>

                      <v-text-field
                        label="Confirm Password"
                        type="password"
                        variant="outlined"
                      ></v-text-field>

                      <v-btn class="mt-2" type="submit" block>Submit</v-btn>
                    </v-form>
                    <v-divider class="my-5"></v-divider>
                    <h5 class="text-center">
                      Already have an account? <RouterLink to="/login">Login</RouterLink>
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
