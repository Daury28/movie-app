<script context='module'>
	const apiKey = '8523864c20da85690e867e7cab2a6570';

	export async function load({fetch}) {
		const response = await fetch(`https://api.themoviedb.org/3/movie/popular?api_key=${apiKey}&language=en-US&page=1`)
	
		const data = await response.json();

		if (response.ok) {
			return {
				props: {popularMovies: data.results}
			}
		}

		return {
			status: res.status,
			error: new Error(`Could not load ${url}`)
		};
	}
</script>

<script>
	import PopularMovies from '../components/PopularMovies.svelte';
	import {fly} from 'svelte/transition';
	export let popularMovies;
</script>

<section in:fly={{y:50, duration:500}} out:fly={{y:20, duration:200}}>
  <PopularMovies {popularMovies} />
</section>