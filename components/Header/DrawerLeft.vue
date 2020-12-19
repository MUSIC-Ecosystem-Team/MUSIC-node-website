<template>
  <v-navigation-drawer v-model="show" fixed temporary app @input="changeDrawer">
    <v-list-item>
      <v-list-item-content class="text-center" style="margin-top: 10px">
        <v-list-item-title class="title">{{ title }}</v-list-item-title>
      </v-list-item-content>
    </v-list-item>
    <v-list dense>
      <v-list-item
        v-for="item in menuListItems"
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
  name: 'DrawerLeft',

  props: {
    value: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      show: false,
      title: 'MUSIC!',
      menuListItems: [
        { title: 'Accueil', icon: 'mdi-home', to: '/' },
        {
          title: 'Bibliothèque musicale',
          icon: 'mdi-music-box-multiple',
          to: '/musics',
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
