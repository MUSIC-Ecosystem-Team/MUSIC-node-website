<template>
  <v-menu bottom min-width="200px" rounded offset-y>
    <template #activator="{ on }">
      <v-btn icon x-large v-on="on">
        <v-avatar color="primary" size="38">
          <span class="white--text">PD</span>
        </v-avatar>
      </v-btn>
    </template>
    <v-card>
      <v-list-item-content class="justify-center">
        <!-- Avatar -->
        <div class="mx-auto text-center">
          <v-avatar color="primary" size="38">
            <span class="white--text">PD</span>
          </v-avatar>
          <h3>Nom d'utilisateur</h3>
          <v-divider class="my-3"></v-divider>
          <v-btn depressed rounded text> Editer le compte </v-btn>
          <v-divider class="my-3"></v-divider>
          <v-btn depressed rounded text> Se déconnecter </v-btn>
        </div>
      </v-list-item-content>
    </v-card>
  </v-menu>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'MenuProfile',
})
</script>
