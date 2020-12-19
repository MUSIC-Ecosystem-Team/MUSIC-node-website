<template>
  <v-list-item-icon>
    <v-btn v-if="play" fab medium color="primary">
      <v-icon color="white">mdi-pause</v-icon>
    </v-btn>
    <v-btn v-else fab medium color="primary">
      <v-icon color="white">mdi-play</v-icon>
    </v-btn>
  </v-list-item-icon>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'PlayPauseBtn',
  props: {
    play: {
      type: Boolean,
      required: true,
    },
  },
})
</script>
