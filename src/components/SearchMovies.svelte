<script>
  let input = '';
  import {goto} from '$app/navigation'

  function submitSearch() {
    goto(`/search/${input}`)
  }
</script>

<form on:submit|preventDefault={submitSearch} class="search">
  <label for="search-movie">Search Movies</label>
  <input bind:value={input} name="search-movie" placeholder="Search for movies..." type="text" />
  <button>Search</button>
</form>

<style>

  form {
    margin:0;
    display:flex;
    align-items:center;
    gap:10px;
  }

  label {
    display:block;
    color:#222222;
    font-weight:bold;
    margin-bottom:.5rem;
    visibility:hidden;
    position:absolute;
  }

  input {
    background-color:#f7f7f7;
    color:#222222;
    border-radius:9999px;
    border:1px solid #cccccc;
    padding:.7rem 1.4rem;
    outline:0;
    /* width:250px; */
  }

  input:focus {
    border:1px solid #a0a0a0;
  }

</style>