<template>
  <v-list-item-icon>
    <v-menu offset-x z-index="251" auto>
      <template #activator="{ on, attrs }">
        <v-btn icon v-bind="attrs" v-on="on">
          <v-icon>mdi-volume-high</v-icon>
        </v-btn>
      </template>
      <v-card height="189">
        <v-slider v-model="volume" step="0.01" max="1" vertical />
      </v-card>
    </v-menu>
  </v-list-item-icon>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'VolumeBtn',
  props: {
    value: {
      type: Number,
      required: true,
    },
  },
  data() {
    return {
      volume: 0.5,
    }
  },
  watch: {
    value(val: number) {
      this.volume = val
    },
    volume(val: number) {
      console.log(val)
    },
  },
})
</script>
