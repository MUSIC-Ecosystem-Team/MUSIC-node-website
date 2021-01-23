<template>
  <v-container fluid fill-height class="container fill-height">
    <v-row align="center" justify="center">
      <v-col class="colFlex">
        <v-stepper v-model="e1">
          <v-stepper-header>
            <v-stepper-step :complete="e1 > 1" step="1">
              Création du compte
            </v-stepper-step>

            <v-divider></v-divider>

            <v-stepper-step :complete="e1 > 2" step="2">
              Avatar
            </v-stepper-step>

            <v-divider></v-divider>

            <v-stepper-step step="3">
              Ajout de vos premières musiques
            </v-stepper-step>
          </v-stepper-header>

          <v-stepper-items>
            <v-stepper-content step="1">
              <v-card class="mb-12" tile>
                <v-text-field label="Nom d'utilisateur"></v-text-field>
                <v-text-field
                  label="Mot de passe"
                  type="password"
                ></v-text-field>
                <v-text-field
                  label="Mot de passe"
                  type="password"
                ></v-text-field>
              </v-card>

              <v-btn color="primary" @click="e1 = 2"> Continuer </v-btn>

              <v-btn text> Revenir en arrière </v-btn>
            </v-stepper-content>

            <v-stepper-content step="2">
              <v-card class="mb-12">
                <v-hover>
                  <template #default="{ hover }">
                    <v-avatar size="334">
                      <img alt="Avatar" src="/cover.jpg" />
                      <v-fade-transition>
                        <v-overlay v-if="hover" absolute color="#036358">
                          <v-btn color="primary" @click="selectImage"
                            >Changer d'avatar</v-btn
                          >
                          <input
                            v-show="false"
                            ref="image"
                            type="file"
                            accept="image/*"
                            @change="imageSelected"
                          />
                        </v-overlay>
                      </v-fade-transition>
                    </v-avatar>
                  </template>
                </v-hover>
              </v-card>

              <v-btn color="primary" @click="e1 = 3"> Continuer </v-btn>

              <v-btn text> Revenir en arrière </v-btn>
            </v-stepper-content>

            <v-stepper-content step="3">
              <v-card
                class="mb-12"
                color="grey lighten-1"
                height="200px"
              ></v-card>

              <v-btn color="primary" @click="e1 = 1"> Continuer </v-btn>

              <v-btn text> Revenir en arrière </v-btn>
            </v-stepper-content>
          </v-stepper-items>
        </v-stepper>
      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  layout: 'get-started',
  data() {
    return {
      e1: 1,
      avatar: null,
    }
  },
  methods: {
    selectImage() {},
    imageSelected(e: any) {},
  },
})
</script>

<style scoped>
.container {
  display: block;
  position: fixed;
  text-align: center;
  z-index: 10;
}
.colFlex {
  display: flex;
  justify-content: center;
}
.v-sheet.v-card:not(.v-sheet--outlined) {
  box-shadow: 0px 0px 0px 0px rgba(0, 0, 0, 0.2),
    0px 0px 0px 0px rgba(0, 0, 0, 0.14), 0px 0px 0px 0px rgba(0, 0, 0, 0.12);
}
</style>
