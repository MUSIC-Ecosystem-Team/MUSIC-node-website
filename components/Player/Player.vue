<template>
  <v-card id="playerBar">
    <v-bottom-sheet
      v-model="sheet"
      attach
      persistent
      no-click-animation
      inset
      hide-overlay
      max-width="100%"
    >
      <v-card tile>
        <v-row>
          <v-col cols="auto">
            <v-img src="./cover.jpg" max-height="87" max-width="87" />
          </v-col>
          <v-col>
            <v-progress-linear
              class="my-0"
              height="3"
              color="primary"
            ></v-progress-linear>

            <v-list>
              <v-list-item>
                <v-row justify="center" align="center">
                  <v-col>
                    <v-list-item-content style="margin-left: 10px">
                      <v-list-item-title>Ne joue pas</v-list-item-title>
                      <v-list-item-subtitle>test</v-list-item-subtitle>
                    </v-list-item-content>
                  </v-col>
                  <v-col id="colControlPlayer" class="text-center">
                    <LoopBtn :loop="false" />
                    <PreviousBtn :has-previous="true" />

                    <PlayPauseBtn :play="true" />

                    <SkipBtn :has-next="true" />

                    <ShuffleBtn :shuffle="false" />
                  </v-col>

                  <v-col class="text-right">
                    <v-list-item-icon>
                      <v-menu offset-x z-index="251" auto>
                        <template #activator="{ on, attrs }">
                          <v-btn icon v-bind="attrs" v-on="on">
                            <v-icon>mdi-volume-high</v-icon>
                          </v-btn>
                        </template>
                        <v-card height="189">
                          <v-slider step="0.01" max="1" vertical />
                        </v-card>
                      </v-menu>
                    </v-list-item-icon>
                    <v-list-item-icon id="btnPlaylist" class="ml-0">
                      <v-btn icon>
                        <v-icon>mdi-playlist-music</v-icon>
                      </v-btn>
                    </v-list-item-icon>
                  </v-col>
                </v-row>
              </v-list-item>
            </v-list>
          </v-col>
        </v-row>
      </v-card>
    </v-bottom-sheet>
  </v-card>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'Player',
  data() {
    return {
      sheet: true,
    }
  },
})
</script>

<style scoped>
.col-xl,
.col-xl-auto,
.col-xl-12,
.col-xl-11,
.col-xl-10,
.col-xl-9,
.col-xl-8,
.col-xl-7,
.col-xl-6,
.col-xl-5,
.col-xl-4,
.col-xl-3,
.col-xl-2,
.col-xl-1,
.col-lg,
.col-lg-auto,
.col-lg-12,
.col-lg-11,
.col-lg-10,
.col-lg-9,
.col-lg-8,
.col-lg-7,
.col-lg-6,
.col-lg-5,
.col-lg-4,
.col-lg-3,
.col-lg-2,
.col-lg-1,
.col-md,
.col-md-auto,
.col-md-12,
.col-md-11,
.col-md-10,
.col-md-9,
.col-md-8,
.col-md-7,
.col-md-6,
.col-md-5,
.col-md-4,
.col-md-3,
.col-md-2,
.col-md-1,
.col-sm,
.col-sm-auto,
.col-sm-12,
.col-sm-11,
.col-sm-10,
.col-sm-9,
.col-sm-8,
.col-sm-7,
.col-sm-6,
.col-sm-5,
.col-sm-4,
.col-sm-3,
.col-sm-2,
.col-sm-1,
.col,
.col-auto,
.col-12,
.col-11,
.col-10,
.col-9,
.col-8,
.col-7,
.col-6,
.col-5,
.col-4,
.col-3,
.col-2,
.col-1 {
  padding: 0px;
}

.v-image.v-responsive {
  margin-left: 12px;
}

#colControlPlayer {
  margin: 0px 0;
  margin-right: 100px;
}

.v-list.v-sheet {
  height: 100%;
}

.v-list-item {
  height: 100%;
}

.v-list-item__icon {
  margin: 0px 0;
  margin-right: 0px !important;
  margin-left: 0px !important;
}

#btnPlaylist {
  margin-right: 20px !important;
}

#playerBar {
  z-index: 250 !important;
}
</style>
