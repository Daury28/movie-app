<script>
  export let movie;
</script>

<a href={`/movie/${movie.id}`} class="movie-card">
  <img src={`https://image.tmdb.org/t/p/w300${movie.poster_path}`} alt={movie.title} />
  <div class="description">
    <h3>{movie.title}</h3>
    <p>{movie.release_date}</p>
  </div>
</a>

<style>
  .movie-card {
    display:flex;
    flex-direction:column;
    background:#f1f1f1;
    padding:10px;
    border-radius:2px;
    text-decoration:none;
  }

  img {
    border-radius:2px;
    overflow:hidden;
    max-width:100%;
    height:auto;
  }

  h3 {
    margin:.5rem 0 .3rem 0;
    color:#222222;
    font-size:1rem;
  }

  p {
    margin:0;
    color:#666666;
    font-size:.8rem;
  }
</style>