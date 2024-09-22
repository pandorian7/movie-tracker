<script>
    export let options;
    const {active, loggedIn} = options;
</script>

<nav class="navbar navbar-expand-lg bg-dark" data-bs-theme="dark">
    <div class="container-fluid">
        <a class="navbar-brand" href="/">M-Tracker</a>
        <button
            class="navbar-toggler"
            type="button"
            data-bs-toggle="collapse"
            data-bs-target="#navbarSupportedContent"
            aria-controls="navbarSupportedContent"
            aria-expanded="false"
            aria-label="Toggle navigation"
        >
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li class="nav-item">
                    <a
                        class="nav-link"
                        class:active={active == "home"}
                        aria-current="page"
                        id="nav-link-home"
                        href="/moives">Home</a
                    >
                </li>
                <li class="nav-item">
                    <a
                        class="nav-link"
                        aria-current="page"
                        href="/moives"
                        class:active={active == "movies"}>Movies</a
                    >
                </li>
                <li class="nav-item">
                    <a
                        class="nav-link"
                        href="/shows"
                        class:active={active == "shows"}>Shows</a
                    >
                </li>
            </ul>
            <ul class="navbar-nav d-flex">
                <li class="mx-2">
                    <button class="btn btn-success"
                        ><svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="14"
                            height="14"
                            fill="currentColor"
                            class="bi bi-search"
                            viewBox="0 0 16 16"
                        >
                            <path
                                d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001q.044.06.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1 1 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0"
                            />
                        </svg>
                        Search
                        <code class="badge text-bg-secondary" id="shortcut"
                            >Ctrl+K</code
                        ></button
                    >
                </li>
                {#if loggedIn}
                    <li class="nav-item">
                        <div class="btn-group">
                            <button type="button" class="btn btn-outline-light"
                                >Watchlist</button
                            >
                            <button
                                type="button"
                                class="btn btn-outline-light dropdown-toggle"
                                data-bs-toggle="dropdown"
                            >
                            </button>
                            <ul class="dropdown-menu">
                                <li>
                                    <a class="dropdown-item" href="/lists"
                                        >Profile</a
                                    >
                                </li>
                                <li>
                                    <a class="dropdown-item" href="/lists"
                                        >Lists</a
                                    >
                                </li>
                            </ul>
                        </div>
                    </li>
                {:else}
                    <li class="mx-2">
                        <button type="button" class="btn btn-outline-light">
                            Login With <svg
                                xmlns="http://www.w3.org/2000/svg"
                                width="14"
                                height="14"
                                fill="currentColor"
                                class="bi bi-google"
                                viewBox="0 0 16 16"
                            >
                                <path
                                    d="M15.545 6.558a9.4 9.4 0 0 1 .139 1.626c0 2.434-.87 4.492-2.384 5.885h.002C11.978 15.292 10.158 16 8 16A8 8 0 1 1 8 0a7.7 7.7 0 0 1 5.352 2.082l-2.284 2.284A4.35 4.35 0 0 0 8 3.166c-2.087 0-3.86 1.408-4.492 3.304a4.8 4.8 0 0 0 0 3.063h.003c.635 1.893 2.405 3.301 4.492 3.301 1.078 0 2.004-.276 2.722-.764h-.003a3.7 3.7 0 0 0 1.599-2.431H8v-3.08z"
                                />
                            </svg>
                        </button>
                    </li>
                {/if}
            </ul>
        </div>
    </div>
</nav>

<style>
    code#shortcut {
        opacity: 0.7;
    }
</style>
