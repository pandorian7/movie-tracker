<!-- from https://svelte.dev/repl/48bd3726b74c4329a186838ce645099b?version=3.46.4 -->

<script>

    import bootstrap from 'bootstrap/dist/js/bootstrap';

    import { onMount } from 'svelte';

    let is_ctrl_down = false;
    let is_k_down = false;
    let Model;

    onMount(() => Model = new bootstrap.Modal('#searchModel', {}));
    
    function on_bind() {
        Model.toggle();
    }

    function on_key_down(event) {
        if (event.repeat) return;

        switch (event.key) {
            case "Control":
                is_ctrl_down = true;

                event.preventDefault();
                break;

            case "k":
                is_k_down = true;

                event.preventDefault();
                break;
        }

        if (is_ctrl_down && is_k_down) {
            on_bind();
        }
    }

    function on_key_up(event) {

        switch (event.key) {
            case "Control":
                is_ctrl_down = false;

                event.preventDefault();
                break;

            case "k":
                is_k_down = false;

                event.preventDefault();
                break;
        }
    }

</script>

<svelte:window
    on:keydown={on_key_down}
    on:keyup={on_key_up}
/>