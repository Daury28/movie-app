<script context='module'>
	const apiKey = '8523864c20da85690e867e7cab2a6570';

	export async function load({fetch, page}) {
    let movieId = page.params.id;
		const response = await fetch(`https://api.themoviedb.org/3/movie/${movieId}?api_key=${apiKey}&language=en-US&page=1`)
	
		const data = await response.json();
    // console.log(data)

		if (response.ok) {
			return {
				props: { movie: data }
			}
		}

    return {
			status: res.status,
			error: new Error(`Could not load ${url}`)
		};
	}
</script>

<script>
  export let movie;
</script>

<div class="movie-details">
  <div class="image">
    <img src={`https://image.tmdb.org/t/p/original${movie.backdrop_path}`} alt={movie.title} />
  </div>
  <div class="text">
    <h1>{movie.title}</h1>
    <p>{movie.overview}</p>
  </div>
</div>

<a class="button" href="/">Home</a>


<style>
  .movie-details {
    margin-bottom:2rem;
  }

  img {
    max-width:100%;
  }
</style>