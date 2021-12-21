<template>
  <v-container>
    <dialog-modify-music
      :dialog="dialogModifyMusic"
      @clicked="dialogModifyMusicSwitch()"
    />
    <v-btn @click="dialogModifyMusicSwitch()">dialog-modify-music</v-btn>

    <dialog-delete-music
      :dialog="dialogDeleteMusic"
      @clicked="dialogDeleteMusicSwitch()"
    />
    <v-btn @click="dialogDeleteMusicSwitch()">dialog-delete-music</v-btn>

    <dialog-modify-album
      :dialog="dialogModifyAlbum"
      @clicked="dialogModifyAlbumSwitch()"
    />
    <v-btn @click="dialogModifyAlbumSwitch()">dialog-modify-album</v-btn>

    <dialog-modify-playlist
      :dialog="dialogModifyPlaylist"
      @clicked="dialogModifyPlaylistSwitch()"
    />
    <v-btn @click="dialogModifyPlaylistSwitch()">dialog-modify-playlist</v-btn>

    <dialog-new-playlist
      :dialog="dialogNewPlaylist"
      @clicked="dialogNewPlaylistSwitch()"
    />
    <v-btn @click="dialogNewPlaylistSwitch()">dialog-new-playlist</v-btn>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      dialogModifyMusic: false,
      dialogDeleteMusic: false,
      dialogModifyAlbum: false,
      dialogModifyPlaylist: false,
      dialogNewPlaylist: false,
    }
  },
  methods: {
    dialogModifyMusicSwitch() {
      if (this.dialogModifyMusic) {
        this.dialogModifyMusic = false
      } else {
        this.dialogModifyMusic = true
      }
    },
    dialogDeleteMusicSwitch() {
      if (this.dialogDeleteMusic) {
        this.dialogDeleteMusic = false
      } else {
        this.dialogDeleteMusic = true
      }
    },
    dialogModifyAlbumSwitch() {
      if (this.dialogModifyAlbum) {
        this.dialogModifyAlbum = false
      } else {
        this.dialogModifyAlbum = true
      }
    },
    dialogModifyPlaylistSwitch() {
      if (this.dialogModifyPlaylist) {
        this.dialogModifyPlaylist = false
      } else {
        this.dialogModifyPlaylist = true
      }
    },
    dialogNewPlaylistSwitch() {
      if (this.dialogNewPlaylist) {
        this.dialogNewPlaylist = false
      } else {
        this.dialogNewPlaylist = true
      }
    },
  },
}
</script>

<style></style>
