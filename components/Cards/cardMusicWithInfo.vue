<template>
  <v-hover v-slot="{ hover }">
    <v-card
      tile
      max-width="190"
      :class="{ 'on-hover': hover }"
      :elevation="hover ? 11 : 2"
    >
      <v-img src="./cover.jpg">
        <v-row class="fill-height flex-column" justify="space-between">
          <div class="align-self-end">
            <menu-playlist :hover="hover" :playlists="[]" />
          </div>
          <div class="align-self-end">
            <v-btn
              :class="{ 'show-btn-play-background': hover }"
              fab
              x-small
              depressed
              style="margin-right: 20px; margin-bottom: 8px"
              color="transparent"
            >
              <v-icon :class="{ 'show-btn-play': hover }" color="transparent">
                mdi-play
              </v-icon>
            </v-btn>
          </div>
        </v-row></v-img
      >
      <v-card-title class="titleCard"> Title </v-card-title>
      <v-card-subtitle class="subtitleCard"> Type </v-card-subtitle>
    </v-card>
  </v-hover>
</template>

<script>
export default {
  name: 'cardMusicWithInfo',

  props: {
    music_info: {
      type: Object,
      require: true,
      required: true,
    },
  },
  data() {
    return {}
  },
}
</script>

<style scoped>
.v-card__subtitle.text-truncate.d-block {
  padding: 16px !important;
  padding-top: 0px !important;
}

.row.fill-height.flex-column.justify-space-between {
  margin-top: 1px;
}

.titleCard,
.subtitleCard {
  font-size: 13px;
  line-height: 1rem;
}
</style>
