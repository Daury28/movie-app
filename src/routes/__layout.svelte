<header>
  <div class="brand">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/1b/Svelte_Logo.svg/30px-Svelte_Logo.svg.png" />
    Movies
  </div>
  <div class="search-movies">
    <SearchMovies />
  </div>
</header>

<div class="container">
  <slot />
</div>

<script>
  import '../app.css';
	import SearchMovies from '../components/SearchMovies.svelte';
</script>

<style>
	header {
		display:flex;
		justify-content:space-between;
		align-items:center;
		padding-bottom:1.5rem;
		margin-bottom:1.3rem;
		border-bottom:1px solid #eeeeee;
	}

	.brand {
		display:flex;
		align-items:center;
		gap:10px;
		color:#222222;
		font-weight:bold;
		font-size:1.5rem;
		width:30%;
	}

	.search-movies {
		width:70%;
		display:flex;
		justify-content: flex-end;
	}

	.brand img {
		width:30px;
	}
</style>