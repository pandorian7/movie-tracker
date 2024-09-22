<script>
    import MovieCard from "./components/movieCard.svelte";
    import movies from "./assests/movies.json";
    let movie = movies[0];
</script>

<div><MovieCard {movie} /></div>

<style>
    div {
        margin: 10px;
    }
</style>
