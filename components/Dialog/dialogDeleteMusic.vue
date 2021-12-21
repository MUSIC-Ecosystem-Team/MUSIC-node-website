<template>
  <v-dialog
    v-model="dialog"
    width="600"
    @click:outside="$emit('clicked', false)"
  >
    <v-card tile>
      <v-card-title> Supprimer définitivement le titre </v-card-title>

      <v-card-text>
        Voulez-vous vraiment <strong>supprimer définitivement</strong> le titre
      </v-card-text>

      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn color="primary" text @click="dialog = false"> Annuler </v-btn>
        <v-btn color="primary" text @click="dialog = false">
          Supprimer l'album
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  name: 'dialogDeleteMusic',

  props: {
    dialog: {
      type: Boolean,
      require: true,
      default: false,
    },
  },
}
</script>

<style></style>
