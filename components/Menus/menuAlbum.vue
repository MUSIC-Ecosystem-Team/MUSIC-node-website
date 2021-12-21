<template>
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
        <v-list-item-title>Lire cet album juste après</v-list-item-title>
      </v-list-item>
      <v-divider></v-divider>
      <v-menu offset-x tile>
        <template #activator="{ on, attrs }">
          <v-list-item>
            <v-list-item-title v-bind="attrs" v-on="on"
              >Ajouter l'album à une playlist</v-list-item-title
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
      <v-divider></v-divider>
      <v-list-item>
        <v-list-item-title
          >Modifier les informations de l'album</v-list-item-title
        >
      </v-list-item>
      <!-- <v-list-item>
        <v-list-item-title
          >Télécharger l'album</v-list-item-title
        >
      </v-list-item> -->
      <v-list-item>
        <v-list-item-title>Supprimer l'album</v-list-item-title>
      </v-list-item>
      <v-list-item>
        <v-list-item-title>Ignorer</v-list-item-title>
      </v-list-item>
    </v-list>
  </v-menu>
</template>

<script>
export default {
  name: 'menuAlbum',
  props: {
    hover: {
      required: true,
    },
    playlists: {
      type: Array,
      required: true,
    },
  },
}
</script>

<style>
i.v-icon.notranslate.mdi.mdi-play.theme--light.transparent--text.show-btn-play {
  color: #ffffff !important;
}
button.v-btn.v-btn--depressed.v-btn--fab.v-btn--round.theme--light.v-size--x-small.transparent.show-btn-play-background {
  background-color: #ffffff !important;
}
i.v-icon.notranslate.mdi.mdi-dots-vertical.theme--light.transparent--text.show-btn {
  color: #ffffff !important;
}
</style>
