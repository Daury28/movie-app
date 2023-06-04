<script context='module'>
	const apiKey = '8523864c20da85690e867e7cab2a6570';

	export async function load({fetch, page}) {
    let searchTerms = page.params.id;
		const response = await fetch(`https://api.themoviedb.org/3/search/movie?api_key=${apiKey}&language=en-US&query=${searchTerms}&page=1&include_adult=false`)
	
		const data = await response.json();
    console.log(data)

		if (response.ok) {
			return {
				props: {searchResults: data.results}
			}
		}

		return {
			status: res.status,
			error: new Error(`Could not load ${url}`)
		};
	}
</script>

<script>
  import MovieCard from '../../components/MovieCard.svelte';
  export let searchResults;
</script>

<div class="search-results">
  <div class="movie-grid">
    {#each searchResults as movie}
      <MovieCard {movie} />
    {/each}
  </div>
</div>

<a class="button" href="/">Home</a>

<style>
  .search-results {
    margin-bottom:2rem;
  }
</style>