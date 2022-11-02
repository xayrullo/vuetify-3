<template>
  <v-select
    v-model="filter.country"
    :items="countries"
    clearable
    label="Filter by country"
  ></v-select>

  <v-select
    v-model="filter.score"
    :items="scores"
    clearable
    label="Filter by score"
  ></v-select>
</template>
<script lang="ts">
import { defineComponent, ref, watch } from 'vue'

interface Filter {
    score: String | null,
    country: String | null
}

export default defineComponent({
    props: {
      countries: Array,
      scores: Array
    },
    setup() {
      const filter = ref<Filter>({
        score: null,
        country: null
      })
      return {
        filter
      }
    },
})
</script>
