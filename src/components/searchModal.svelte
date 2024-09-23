<script>

  import { onMount } from "svelte";

  onMount(() => {
    const Model = document.getElementById("searchModel");
    console.log(Model);
    const searchBox = document.getElementById("searchBox");
    const onShow = () => searchBox.focus();

    Model.addEventListener('shown.bs.modal', onShow); 

    return () => Model.removeEventListener('shown.bs.modal', onShow);
  });

</script>

<div class="modal fade" id="searchModel" tabindex="-1">
  <div class="modal-dialog modal-lg">
    <div class="modal-content">
      <div class="modal-body">
        <input class="form-control" placeholder="Search" id="searchBox" />
      </div>
    </div>
  </div>
</div>
