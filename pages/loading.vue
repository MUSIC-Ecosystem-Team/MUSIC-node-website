<template>
  <v-bottom-sheet id="loadingSheet" v-model="sheet" fullscreen>
    <v-sheet class="text-center" height="100%">
      <v-container fluid class="fill-height">
        <v-row justify="center" align="center">
          <v-col cols="4" justify="center" align="center">
            <v-img max-height="350" max-width="450" src="./newMusic.png" />
            <v-progress-linear
              width="500"
              indeterminate
              color="primary"
            ></v-progress-linear>
          </v-col>
        </v-row>
      </v-container>
    </v-sheet>
  </v-bottom-sheet>
</template>

<script>
export default {
  data() {
    return {
      sheet: true,
    }
  },
}
</script>

<style scoped>
.loadingMessage {
  color: grey;
}
</style>
