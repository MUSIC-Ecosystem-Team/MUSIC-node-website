<template>
  <v-container>
    <v-col class="mt-2" cols="12">
      <h3>Playlists récentes</h3>
    </v-col>
    <v-row>
      <v-col v-for="n in 10" :key="n" xs="7" sm="4" lg="2" md="3">
        <card-music-with-info :music_info="{}" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {}
</script>
