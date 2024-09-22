<script>
    import MovieCard from "./movieCard.svelte";
    export let movies;
</script>

<div id="movies">
    {#each movies as movie}
        <div id="movie">
            <MovieCard {movie} />
        </div>
    {/each}
</div>

<style>
    #movies {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(13rem, 1fr));
        row-gap: 10px;
    }
    #movie {
        display: flex;
        justify-content: center;
    }
</style>