<script>
  import MovieCard from "#lib/components/MovieCard.svelte";

  let { data } = $props();
  let movie = $derived(data.movie);
</script>
<a href= "/movies">Back</a>

<h1>{data.movie.title}</h1>

<div class ="row">
<div class="col-sm-6 col-md-4 col-lg-3 mb-2 gx-2">
  <img class="img-fluid" src={movie.poster} alt="" />
</div>

<div class= "col">
<div class= "mb-3">Jahr: {data.movie.year}</div>
<div class= "mb-3">Dauer: {data.movie.length}</div>
<div>Cast:</div>
<ul>
    {#each movie.actors as actor}
      <li>{actor}</li>
    {/each}
</ul>
</div>
</div>