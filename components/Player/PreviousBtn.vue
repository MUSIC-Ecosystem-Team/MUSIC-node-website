<template>
  <v-list-item-icon>
    <v-btn icon :disabled="!hasPrevious">
      <v-icon>mdi-rewind</v-icon>
    </v-btn>
  </v-list-item-icon>
</template>

<script>
export default {
  name: 'PreviousBtn',
  props: {
    hasPrevious: {
      type: Boolean,
      required: true,
    },
  },
}
</script>
