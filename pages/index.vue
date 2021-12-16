<template>
  <v-container>
    <h1>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. In omnis eaque,
      itaque deleniti praesentium dolorem nihil, fuga cum, molestias minus eos.
      At explicabo aspernatur laborum. Numquam delectus soluta voluptas
      architecto!
    </h1>
    <v-row>
      <v-col v-for="n in 10" :key="n" xs="7" sm="4" lg="2" md="3">
        <card-music :music_info="{}"></card-music>
      </v-col>
    </v-row>
    <dialog-modify-album />
    <dialog-modify-music />
  </v-container>
</template>

<script>
import dialogModifyMusic from '~/components/dialogModifyMusic.vue'
export default {
  components: { dialogModifyMusic },
}
</script>
