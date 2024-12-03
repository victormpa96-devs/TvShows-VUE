<template>
  <div id="main" class="d-flex flex-column p-4 rounded">
    <b-form-input
      v-model="searchQuery"
      placeholder="Searching TV-Shows..."
      size="lg"
      class="searchBar mb-4"
      :state="searchQuery.length > 0 ? true : null"
    ></b-form-input>

    <b-row
      class="rounded d-flex flex-row flex-grow-1 align-items-center justify-content-center gap-2 p-2"
    >
      <b-col
        v-for="(tvshow, index) in filteredSeries"
        :key="index"
        cols="12" sm="6" md="4" lg="3"
        class="flex-grow-1 p-0"
      >
        <b-card
          :title="tvshow.name"
          :sub-title="`${tvshow.seasons} Seasons`"
          class=""
        >
          <b-card-text>
            <p><strong>Genre:</strong> {{ tvshow.genre }}</p>
            <p><strong>Year:</strong> {{ tvshow.year }}</p>
            <p><strong>Status:</strong> {{ tvshow.status }}</p>
          </b-card-text>
        </b-card>
      </b-col>
    </b-row>
  </div>
</template>

<script>
import { BFormInput, BCard, BCardText, BRow, BCol } from 'bootstrap-vue'
import TvSeries from '@/components/TvSeries'

export default {
  name: 'home',
  components: {
    TvSeries,
    BFormInput,
    BCard,
    BCardText,
    BRow,
    BCol
  },
  data () {
    return {
      searchQuery: '',
      tvShows: [
        {
          name: 'Game of Thrones',
          seasons: 8,
          genre: 'Fantasy',
          year: 2011,
          status: 'Ended'
        },
        {
          name: 'Breaking Bad',
          seasons: 5,
          genre: 'Drama',
          year: 2008,
          status: 'Ended'
        },
        {
          name: 'LOST',
          seasons: 6,
          genre: 'Mystery',
          year: 2004,
          status: 'Ended'
        },
        {
          name: 'Silicon Valley',
          seasons: 4,
          genre: 'Comedy',
          year: 2014,
          status: 'Ended'
        }
      ]
    }
  },
  computed: {
    filteredSeries () {
      return this.tvShows.filter(series =>
        series.name.toLowerCase().includes(this.searchQuery.toLowerCase())
      )
    }
  }
}
</script>

<style scoped>
#main {
  background-color: #7e8afe;
}

.searchBar{
  border: 5px solid #18264e;
  background-color: #c4c4ff;
  color: #18264e
}

.row{
  background-color: #282d4c;
}

.card{
  background-color: #c4c4ff;
}
</style>
