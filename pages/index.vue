<template>
  <div class="home">
    <Hero />
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      movie: [],
    }
  },
  async fetch() {
    await this.getMovies()
  },
  methods: {
    async getMovies() {
      const data= axios.get('https://api.themoviedb.org/3/movie/now_playing?api_key=37ed43a4f8eaa2abd75f9283692947bc&language=en-US&page=1')
      const result = await data
      result.data.results.forEach((movie) => {this.movies=(movie)})
      console.log(this.movies)
    }
  }
}
</script>

<style>
</style>

