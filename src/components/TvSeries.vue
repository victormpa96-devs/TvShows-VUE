<template>
  <b-row>
    <b-col
      v-for="(tvshow, index) in tvShows"
      :key="index"
      cols="12" sm="6" md="4" lg="3"
      class="mb-4"
    >
      <b-card :title="tvshow.name" :sub-title="`${tvshow.seasons} Seasons`" class="h-100">
        <b-card-text>
          <p><strong>Genre:</strong> {{ tvshow.genre }}</p>
          <p><strong>Year:</strong> {{ tvshow.year }}</p>
          <p><strong>Status:</strong> {{ tvshow.status }}</p>
        </b-card-text>
      </b-card>
    </b-col>
  </b-row>
</template>

<script>
import { BCard, BCardText, BRow, BCol } from 'bootstrap-vue'

export default {
  name: 'tv-series',
  components: {
    BCard,
    BCardText,
    BRow,
    BCol
  },
  props: ['tvShows']
}
</script>
