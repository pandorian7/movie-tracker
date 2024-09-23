<script>
    import {
        Navbar,
        NavbarBrand,
        NavbarToggler,
        Collapse,
        Nav,
        NavItem,
        NavLink,
        Button,
    } from "@sveltestrap/sveltestrap";

    let isOpen = false;
    export let active;
    export let loggedIn;

    function handleUpdate(event) {
        isOpen = event.detail.isOpen;
    }
</script>

<Navbar container="fluid" color="dark" theme="dark" expand="lg">
    <NavbarBrand href="/">M-Tracker</NavbarBrand>
    <NavbarToggler on:click={() => (isOpen = !isOpen)} />
    <Collapse {isOpen} navbar expand="md" on:update={handleUpdate}>
        <Nav class="me-auto mb-2 mb-lg-0" navbar>
            <NavItem>
                <NavLink href="/home" active={active == "home"}>Home</NavLink>
            </NavItem>
            <NavItem>
                <NavLink href="/movies" active={active == "movies"}
                    >Movies</NavLink
                >
            </NavItem>
            <NavItem>
                <NavLink href="/series" active={active == "series"}
                    >Series</NavLink
                >
            </NavItem>
        </Nav>
        <Nav class="d-flex" navbar>
            <NavItem>
                <Button color="success"
                    ><i class="bi bi-search" style="font-size: 14px;"></i>
                    Search
                    <code class="badge text-bg-secondary" id="shortcut"
                        >Ctrl+K</code
                    ></Button
                >
            </NavItem>
        </Nav>
    </Collapse>
</Navbar>

<style>
    code#shortcut {
        opacity: 0.7;
    }
</style>
