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
                      <v-list-item-title
                        class="titlePlayer"
                        style="max-width: 150px"
                        >Lorem ipsum dolor, sit amet consectetur adipisicing
                        elit. Odio, blanditiis deleniti, tempora illo ratione,
                        explicabo odit unde delectus iusto magnam soluta ea
                        molestiae consequatur ipsam enim incidunt quis officiis
                        tenetur!</v-list-item-title
                      >
                      <v-list-item-subtitle
                        class="artistPlayer"
                        style="max-width: 150px"
                        >Lorem ipsum dolor, sit amet consectetur adipisicing
                        elit. Fuga, error! Eligendi, officia pariatur. Iste modi
                        ea in aliquid. Voluptas sequi non aliquid consequatur
                        illo, illum veniam odit obcaecati alias
                        inventore.</v-list-item-subtitle
                      >
                    </v-list-item-content>
                  </v-col>
                  <v-col id="colControlPlayer" class="text-center">
                    <loop-btn :loop="false" />
                    <previous-btn :has-previous="true" />

                    <play-pause-btn :play="true" />

                    <skip-btn :has-next="true" />

                    <shuffle-btn :shuffle="false" />
                  </v-col>

                  <v-col class="text-right">
                    <volume-btn :value="0" />
                    <queue-btn />
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

<script>
import LoopBtn from './LoopBtn.vue'
import PlayPauseBtn from './PlayPauseBtn.vue'
import PreviousBtn from './PreviousBtn.vue'
import QueueBtn from './QueueBtn.vue'
import ShuffleBtn from './ShuffleBtn.vue'
import SkipBtn from './SkipBtn.vue'
import VolumeBtn from './VolumeBtn.vue'

export default {
  components: {
    LoopBtn,
    PreviousBtn,
    PlayPauseBtn,
    SkipBtn,
    VolumeBtn,
    QueueBtn,
    ShuffleBtn,
  },
  name: 'Player',
  data() {
    return {
      sheet: true,
    }
  },
}
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

.v-list-item.theme--light {
  padding-bottom: 16px;
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

.titlePlayer {
  width: 150px;
  max-width: 100%;
}

.artistPlayer {
  width: 150px;
  max-width: 100%;
}
</style>
