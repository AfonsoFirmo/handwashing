<script>
  import Progressbar from "./Progressbar.svelte";
</script>

<div bp="grid">
  <h2 bp="offset-5@md 4@md 12@sm">Seconds Left:</h2>
</div>

<Progressbar />

<div bp="grid">
  <button bp="offset-5@md 4@md 12@sm" class="start" type="button"
    >Start Washing</button
  >
</div>

<style>
  h2 {
    margin: 0;
  }

  .start {
    background-color: green;
    width: 100%;
  }
</style>
