<template>
  <v-dialog v-model="dialog" width="600">
    <template v-slot:activator="{ on, attrs }">
      <v-btn color="red lighten-2" dark v-bind="attrs" v-on="on">
        Click Me
      </v-btn>
    </template>

    <v-card tile>
      <v-card-title> Modifier les informations de l'album </v-card-title>

      <v-card-text>
        <v-row>
          <v-col cols="8">
            <v-text-field label="Artiste de l'album"></v-text-field>
            <v-text-field label="Album"></v-text-field>
            <v-text-field label="Compositeur"></v-text-field>
            <v-text-field label="Genre"></v-text-field>
          </v-col>
          <v-col cols="4">
            <v-img
              lazy-src="https://picsum.photos/id/11/10/6"
              height="140"
              width="140"
              src="https://picsum.photos/id/11/500/300"
            ></v-img>
            <v-text-field label="Année"></v-text-field>
            <v-row>
              <v-col>
                <v-text-field label="Titres"></v-text-field>
              </v-col>
              <v-col>
                <v-text-field label="Disques"></v-text-field>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-card-text>

      <v-card-actions>
        <v-btn color="primary" text @click="dialog = false">
          Utiliser les suggestions
        </v-btn>
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
  data() {
    return {
      dialog: false,
    }
  },
}
</script>

<style></style>
