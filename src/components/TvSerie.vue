<template>
  <b-card :title="tvshow.name" :sub-title="`${tvshow.seasons} Seasons`" class="h-100">
    <b-card-text>
      <p><strong>Genre:</strong> {{ tvshow.genre }}</p>
      <p><strong>Year:</strong> {{ tvshow.year }}</p>
      <p><strong>Status:</strong> {{ tvshow.status }}</p>
    </b-card-text>
  </b-card>
</template>

<script>
export default {
  name: 'tv-serie',
  props: ['tvshow']
}
</script>
