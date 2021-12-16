<template>
  <v-app-bar
    app
    absolute
    flat
    tile
    :extended="
      $route.fullPath === '/musics' || $route.fullPath === '/musics/'
        ? true
        : false
    "
  >
    <v-app-bar-nav-icon
      @click="$emit('update:drawer-change-left', !drawerLeft)"
    ></v-app-bar-nav-icon>

    <v-toolbar-title>MUSIC!</v-toolbar-title>
    <template v-if="$route.fullPath.split('/')[1] === 'musics'" #extension>
      <v-tabs align-with-title color="primary" hide-slider>
        <v-tab link nuxt to="/musics">PLAYLISTS</v-tab>
        <v-tab link nuxt to="/musics/artists">ARTISTES</v-tab>
        <v-tab link nuxt to="/musics/albums">ALBUMS</v-tab>
        <v-tab link nuxt to="/musics/titles">TITRES</v-tab>
        <v-tab link nuxt to="/musics">GENRES</v-tab>
      </v-tabs>
      <v-spacer></v-spacer>
      <v-btn text
        ><v-icon left>mdi-shuffle</v-icon> LIRE EN MODE ALÉATOIRE</v-btn
      >
    </template>
    <v-spacer></v-spacer>
    <auto-complete-search />
    <v-spacer></v-spacer>
    <v-btn icon @click="$emit('update:drawer-change-right', !drawerRight)">
      <v-icon> mdi-playlist-play </v-icon>
    </v-btn>
    <menu-profile />
  </v-app-bar>
</template>

<script>
import AutoCompleteSearch from './AutoCompleteSearch.vue'
import MenuProfile from './MenuProfile.vue'

export default {
  components: { AutoCompleteSearch, MenuProfile },
  name: 'AppBar',
  props: {
    drawerRight: {
      type: Boolean,
      required: true,
    },
    drawerLeft: {
      type: Boolean,
      required: true,
    },
  },
}
</script>
