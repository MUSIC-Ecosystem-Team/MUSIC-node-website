<template>
  <v-list-item-icon>
    <v-btn icon :disabled="!hasPrevious">
      <v-icon>mdi-rewind</v-icon>
    </v-btn>
  </v-list-item-icon>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'PreviousBtn',
  props: {
    hasPrevious: {
      type: Boolean,
      required: true,
    },
  },
})
</script>
