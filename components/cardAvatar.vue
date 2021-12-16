<template>
  <v-hover v-slot="{ hover }">
    <nuxt-link to="/">
      <v-avatar :class="hover ? 'elevation-11' : 'elevation-4'" size="135">
        <v-img src="./cover.jpg" />
      </v-avatar>
      <div>Inconnu</div>
    </nuxt-link>
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
</style>
