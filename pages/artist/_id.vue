<template>
  <v-main>
    <v-container fluid>
      <!-- Header Page -->
      <v-row>
        <v-col cols="auto">
          <v-avatar size="180">
            <v-img src="./cover.jpg" />
          </v-avatar>
        </v-col>
        <v-col>
          <v-list>
            <v-list-item>
              <v-row justify="center" align="center">
                <v-col>
                  <h1>
                    Ooggle
                    <v-btn outlined fab small>
                      <v-icon>mdi-play</v-icon>
                    </v-btn>
                  </h1>
                  <v-list-item-content>
                    <v-list-item-subtitle>2 albums</v-list-item-subtitle>
                  </v-list-item-content>
                </v-col>
              </v-row>
            </v-list-item>
          </v-list>
        </v-col>
      </v-row>
      <!-- List -->
      <v-row>
        <v-col class="mt-2" cols="12">
          <h3>Ma bibiothèque</h3>
        </v-col>
        <v-col v-for="n in 2" :key="n" xs="7" sm="4" lg="2" md="3">
          <v-hover v-slot="{ hover }">
            <v-card
              tile
              width="190"
              height="190"
              class="mx-auto"
              :class="{ 'on-hover': hover }"
              :elevation="hover ? 11 : 2"
            >
              <v-img src="./cover.jpg" height="190" width="190"
                ><v-row class="fill-height flex-column" justify="space-between">
                  <v-spacer></v-spacer>
                  <div class="align-self-end">
                    <v-btn
                      :class="{ 'show-btn-play-background': hover }"
                      fab
                      x-small
                      depressed
                      style="margin-right: 20px; margin-bottom: 8px"
                      color="transparent"
                    >
                      <v-icon
                        :class="{ 'show-btn-play': hover }"
                        color="transparent"
                      >
                        mdi-play
                      </v-icon>
                    </v-btn>
                  </div>
                </v-row></v-img
              >
              <v-card-title class="body-2 text-truncate d-block">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde
                corrupti obcaecati totam consequatur vero quam harum neque, enim
                illum accusamus quibusdam tempora laborum nihil nulla iste
                molestiae ipsum atque doloremque?</v-card-title
              >

              <v-card-subtitle class="text-truncate text-caption d-block">
                0 titres
              </v-card-subtitle>
            </v-card>
          </v-hover>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<script>
export default {
  data() {
    return {}
  },
}
</script>

<style scopped>
i.v-icon.notranslate.mdi.mdi-play.theme--light.transparent--text.show-btn-play {
  color: rgb(114, 114, 114) !important;
}

button.v-btn.v-btn--depressed.v-btn--fab.v-btn--round.theme--light.v-size--x-small.transparent.show-btn-play-background {
  background-color: #ffffff !important;
}
/* 
.text-truncate {
  -webkit-line-clamp: 1 !important;
  -webkit-box-orient: vertical !important;
  display: -webkit-box !important;
  width: 190px !important;
} */
</style>
