<template>
  <v-list-item-icon>
    <v-btn v-if="loop" icon>
      <v-icon>mdi-repeat</v-icon>
    </v-btn>
    <v-btn v-else icon>
      <v-icon>mdi-repeat-off</v-icon>
    </v-btn>
  </v-list-item-icon>
</template>

<script>
export default {
  name: 'LoopBtn',
  props: {
    loop: {
      type: Boolean,
      required: true,
    },
  },
}
</script>

<style></style>
