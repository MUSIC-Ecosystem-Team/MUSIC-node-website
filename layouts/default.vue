<template>
  <v-app>
    <!-- Navbar -->
    <app-bar
      :drawer-left="drawerLeft"
      :drawer-right="drawerRight"
      :drawer-change-left.sync="drawerLeft"
      :drawer-change-right.sync="drawerRight"
    />
    <!-- Drawer Left -->
    <drawer-left :value="drawerLeft" :change-val.sync="drawerLeft" />
    <!-- Drawer Right -->
    <drawer-right :value="drawerRight" :change-val.sync="drawerRight" />
    <v-main>
      <nuxt keep-alive />
    </v-main>
    <Player />
  </v-app>
</template>

<script>
import AppBar from '~/components/Header/Bar/AppBar.vue'
import DrawerLeft from '~/components/Header/DrawerLeft.vue'
import DrawerRight from '~/components/Header/DrawerRight.vue'

export default {
  components: { AppBar, DrawerLeft, DrawerRight },
  data() {
    return {
      drawerLeft: false,
      drawerRight: false,
    }
  },
}
</script>

<style>
/* width */
::-webkit-scrollbar {
  width: 5px;
}

/* Track */
::-webkit-scrollbar-track {
  background: #f1f1f1;
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: #888;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #555;
}

header.v-sheet.theme--light.rounded-0.v-toolbar.v-toolbar--absolute.v-toolbar--flat.v-app-bar.white {
  border-bottom: 1px solid;
}

.v-application .white {
  border-color: #d3d3d3 !important;
}

main {
  margin-bottom: 86px;
}

@media (min-width: 1264px) {
  .container {
    max-width: 1300px;
  }
}

@media (min-width: 960px) {
  .container {
    max-width: 1300px;
  }
}

.container--fluid {
  max-width: 100% !important;
}

.tableListTitle {
  color: black !important;
  max-width: 400px !important;
}

a {
  color: #757575 !important;
}

a:hover {
  color: #555555 !important;
}

a.underline {
  text-decoration: none !important;
}

a.underline:hover {
  text-decoration: underline !important;
}

.v-card__content {
  padding: 16px 24px 10px !important;
}
</style>
