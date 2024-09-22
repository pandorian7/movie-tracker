<script>
    import NavBar from "./components/navBar.svelte";

    let navBarOptions = {
        active: 'home',
        loggedIn: false
    }

</script>

<NavBar options={navBarOptions}/>
