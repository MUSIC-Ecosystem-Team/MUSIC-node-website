<template>
  <v-dialog
    v-model="dialog"
    width="600"
    @click:outside="$emit('clicked', false)"
  >
    <v-card tile>
      <v-card-title> Modifier la playlist </v-card-title>

      <v-card-text>
        <v-row>
          <v-col>
            <v-text-field label="Nom"></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col>
            <v-textarea
              label="Description"
              counter="500"
              flat
              no-resize
              :rules="[rules.length(500)]"
            ></v-textarea>
          </v-col>
        </v-row>
      </v-card-text>

      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn color="primary" text @click="dialog = false"> Annuler </v-btn>
        <v-btn color="primary" text @click="dialog = false">
          Enregistrer
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  name: 'dialogModifyPlaylist',

  props: {
    dialog: {
      type: Boolean,
      require: true,
      default: false,
    },
  },
  data() {
    return {
      rules: {
        length: (len) => (v) =>
          (v || '').length <= len ||
          `La description ne doit pas dépasser ${len} caractères !`,
      },
    }
  },
}
</script>

<style></style>
