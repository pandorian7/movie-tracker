<script>
    import NavBar from "./components/navBar.svelte";
    import SearchModal from "./components/searchModal.svelte";

    let navBarOptions = {
        active: 'home',
        loggedIn: false
    }

</script>

<NavBar options={navBarOptions}/>
<SearchModal />
