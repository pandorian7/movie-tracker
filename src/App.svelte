<script>
    import NavBar from "./components/navBar.svelte";
    import SearchModal from "./components/searchModal.svelte";
    import Newnav from "./components/newnav.svelte";

    let navBarOptions = {
        active: "home",
        loggedIn: false,
    };
</script>

<!-- <NavBar options={navBarOptions} /> -->
<Newnav active="home" />
<!-- <SearchModal /> -->
