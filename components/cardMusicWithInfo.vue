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
            <v-menu tile>
              <template #activator="{ on, attrs }">
                <v-btn
                  :class="{ 'show-btn': hover }"
                  right
                  icon
                  style="margin-right: 20px; margin-top: 8px"
                  v-bind="attrs"
                  v-on="on"
                >
                  <v-icon :class="{ 'show-btn': hover }" color="transparent">
                    mdi-dots-vertical
                  </v-icon>
                </v-btn>
              </template>

              <v-list dense>
                <v-list-item>
                  <v-list-item-title>Lire en mode aléatoire</v-list-item-title>
                </v-list-item>
                <v-list-item>
                  <v-list-item-title
                    >Lire cette playlist ensuite</v-list-item-title
                  >
                </v-list-item>
                <v-list-item>
                  <v-list-item-title
                    >Ajouter cette playlist à la file
                    d'attente</v-list-item-title
                  >
                </v-list-item>
                <v-divider />
                <v-menu offset-x tile>
                  <template #activator="{ on, attrs }">
                    <v-list-item>
                      <v-list-item-title v-bind="attrs" v-on="on"
                        >Ajouter cette playlist à la playlist</v-list-item-title
                      >
                    </v-list-item>
                  </template>

                  <v-list dense>
                    <v-list-item>
                      <v-list-item-title>Nouvelle playlist</v-list-item-title>
                    </v-list-item>
                    <v-list-item>
                      <v-list-item-title>Rock</v-list-item-title>
                    </v-list-item>
                    <v-list-item>
                      <v-list-item-title>Ooggle JTM</v-list-item-title>
                    </v-list-item>
                  </v-list>
                </v-menu>
                <v-divider />
                <v-list-item>
                  <v-list-item-title>Modifier la playlist</v-list-item-title>
                </v-list-item>
                <v-list-item @click="showDeletePlaylist = true">
                  <v-list-item-title>Supprimer la playlist</v-list-item-title>
                </v-list-item>
              </v-list>
            </v-menu>
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
  name: 'CardMusic',

  props: {
    music_info: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {}
  },
}
</script>

<style scoped>
i.v-icon.notranslate.mdi.mdi-play.theme--light.transparent--text.show-btn-play {
  color: #ffffff !important;
}
button.v-btn.v-btn--depressed.v-btn--fab.v-btn--round.theme--light.v-size--x-small.transparent.show-btn-play-background {
  background-color: #ffffff !important;
}
i.v-icon.notranslate.mdi.mdi-dots-vertical.theme--light.transparent--text.show-btn {
  color: #ffffff !important;
}
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
