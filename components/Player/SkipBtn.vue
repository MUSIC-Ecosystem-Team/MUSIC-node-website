<template>
  <v-list-item-icon>
    <v-btn icon :disabled="!hasNext">
      <v-icon>mdi-fast-forward</v-icon>
    </v-btn>
  </v-list-item-icon>
</template>

<script>
export default {
  name: 'SkipBtn',
  props: {
    hasNext: {
      type: Boolean,
      required: true,
    },
  },
}
</script>
