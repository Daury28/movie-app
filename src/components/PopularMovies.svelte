<script>
  export let popularMovies;
  import MovieCard from './MovieCard.svelte'
</script>

<h2>Popular Movies</h2>

<div class="movie-grid popular-movies">
  {#each popularMovies as movie}
    <MovieCard {movie} />
  {/each}
</div>