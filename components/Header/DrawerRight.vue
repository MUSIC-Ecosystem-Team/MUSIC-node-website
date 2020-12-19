<template>
  <v-navigation-drawer
    v-model="show"
    right
    fixed
    temporary
    app
    @input="changeDrawer"
  >
    <v-list-item class="pt-2">
      <v-list-item-title class="title"> Playlist </v-list-item-title>
      <!-- Btn add Playlist -->
      <v-btn icon>
        <v-icon> mdi-plus </v-icon>
      </v-btn>
    </v-list-item>
    <v-list dense>
      <v-divider></v-divider>
      <v-subheader>Playlists automatiques</v-subheader>
      <v-list-item
        v-for="item in playlistAutoItems"
        :key="item.title"
        nuxt
        :to="item.to"
        color="primary"
      >
        <v-list-item-icon>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-icon>

        <v-list-item-content>
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'DrawerRight',

  props: {
    value: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      show: false,
      playlistAutoItems: [
        { title: "J'aime", icon: 'mdi-thumb-up', to: '/likes' },
        {
          title: 'Derniers ajouts',
          icon: 'mdi-music-box-multiple',
          to: '/latest-add',
        },
      ],
    }
  },
  watch: {
    value(val: boolean) {
      this.show = val
    },
  },
  methods: {
    changeDrawer(val: boolean) {
      this.show = val
      this.$emit('update:changeVal', val)
    },
  },
})
</script>
