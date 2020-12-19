<template>
  <v-list-item-icon>
    <v-btn icon :disabled="!hasNext">
      <v-icon>mdi-fast-forward</v-icon>
    </v-btn>
  </v-list-item-icon>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'SkipBtn',
  props: {
    hasNext: {
      type: Boolean,
      required: true,
    },
  },
})
</script>
