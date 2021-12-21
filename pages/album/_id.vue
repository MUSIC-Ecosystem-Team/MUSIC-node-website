<template>
  <v-main>
    <v-container>
      <!-- Header Page -->
      <v-row>
        <v-col cols="auto">
          <v-img src="./cover.jpg" height="180" width="180" />
        </v-col>
        <v-col>
          <v-list>
            <v-list-item>
              <v-row justify="center" align="center">
                <v-col>
                  <h1>
                    Title Music
                    <v-btn outlined fab small>
                      <v-icon>mdi-play</v-icon>
                    </v-btn>
                  </h1>
                  <v-list-item-content>
                    <v-list-item-subtitle>Artist</v-list-item-subtitle>
                    <v-list-item-subtitle
                      >date - {{ itemsTest.length }} titres -
                      00:00:00</v-list-item-subtitle
                    >
                  </v-list-item-content>
                  <v-btn text class="pa-1"
                    ><v-icon left>mdi-shuffle</v-icon> LIRE EN MODE
                    ALÉATOIRE</v-btn
                  >
                  <v-btn icon>
                    <v-icon>mdi-dots-vertical</v-icon>
                  </v-btn>
                </v-col>
              </v-row>
            </v-list-item>
          </v-list>
        </v-col>
      </v-row>
      <!-- List -->
      <v-row>
        <v-col>
          <v-data-table
            dense
            :headers="headers"
            :items="itemsTest"
            item-key="title"
            locale="fr-FR"
            class="elevation-4 pa-5"
            hide-default-footer
          >
            <template v.slot:[`item.title`]="{ item }">
              <v-list dense color="transparent" class="listDense">
                <v-list-item>
                  <v-row justify="center" align="center">
                    <v-col cols="auto" class="coverTable"
                      ><v-img src="./cover.jpg" height="32" width="32"
                    /></v-col>
                    <v-col class="titleTable">
                      <v-list-item-content style="margin-left: 10px">
                        <v-list-item-title>{{ item.title }}</v-list-item-title>
                      </v-list-item-content>
                    </v-col>
                    <v-spacer></v-spacer>
                    <v-menu tile>
                      <template #activator="{ on, attrs }">
                        <v-btn icon v-bind="attrs" v-on="on">
                          <v-icon>mdi-dots-vertical</v-icon>
                        </v-btn>
                      </template>

                      <v-list dense>
                        <v-list-item>
                          <v-list-item-title
                            >Lire cet album juste après</v-list-item-title
                          >
                        </v-list-item>
                        <v-menu offset-x tile>
                          <template #activator="{ on, attrs }">
                            <v-list-item>
                              <v-list-item-title v-bind="attrs" v-on="on"
                                >Ajouter l'album à une
                                playlist</v-list-item-title
                              >
                            </v-list-item>
                          </template>

                          <v-list dense>
                            <v-list-item>
                              <v-list-item-title>J'aime</v-list-item-title>
                            </v-list-item>
                            <v-list-item>
                              <v-list-item-title>Rock</v-list-item-title>
                            </v-list-item>
                            <v-list-item>
                              <v-list-item-title>Ooggle JTM</v-list-item-title>
                            </v-list-item>
                          </v-list>
                        </v-menu>
                        <v-list-item>
                          <v-list-item-title
                            >Modifier les informations de
                            l'album</v-list-item-title
                          >
                        </v-list-item>
                        <v-list-item>
                          <v-list-item-title
                            >Télécharger l'album</v-list-item-title
                          >
                        </v-list-item>
                        <v-list-item>
                          <v-list-item-title
                            >Supprimer l'album</v-list-item-title
                          >
                        </v-list-item>
                        <v-list-item>
                          <v-list-item-title>Ignorer</v-list-item-title>
                        </v-list-item>
                      </v-list>
                    </v-menu>
                  </v-row>
                </v-list-item>
              </v-list>
            </template></v-data-table
          >
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<script>
export default {
  data() {
    return {
      itemsTest: [
        {
          title: 'Title 1',
          duration: '0:00',
          artist: 'Artist 1',
          album: 'Album 1',
          date: '00/00/0000',
        },
        {
          title: 'Title 2',
          duration: '0:00',
          artist: 'Artist 2',
          album: 'Album 2',
          date: '00/00/0000',
        },
        {
          title: 'Title 3',
          duration: '0:00',
          artist: 'Artist 3',
          album: 'Album 3',
          date: '00/00/0000',
        },
      ],
      headers: [
        {
          text: 'NOM',
          align: 'start',
          sortable: false,
          value: 'title',
        },
        { text: 'DUREE', value: 'duration', sortable: false },
      ],
    }
  },
}
</script>

<style scopped>
.coverTable,
.titleTable,
.listDense {
  padding: 0px !important;
}
table > tbody > tr > th,
table > tbody > tr > td,
table > thead > tr > th {
  border-bottom: thin solid rgba(0, 0, 0, 0) !important;
}

.v-list.listDense.v-sheet.theme--light.v-list--dense:hover {
  background-color: #eeeeee;
}
</style>
