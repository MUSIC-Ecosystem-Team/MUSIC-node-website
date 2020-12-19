<template>
  <v-list-item-icon>
    <v-btn v-if="shuffle" icon>
      <v-icon>mdi-shuffle</v-icon>
    </v-btn>
    <v-btn v-else icon>
      <v-icon>mdi-shuffle-disabled</v-icon>
    </v-btn>
  </v-list-item-icon>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'ShuffleBtn',
  props: {
    shuffle: {
      type: Boolean,
      required: true,
    },
  },
})
</script>

<style></style>
