<template>
  <v-autocomplete
    class="mx-4"
    prepend-inner-icon="mdi-magnify"
    flat
    hide-details
    label="Rechercher"
    solo-inverted
  ></v-autocomplete>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'AutoCompleteSearch',
})
</script>
