<script>
  import { createEventDispatcher } from "svelte";
  import Progressbar from "./Progressbar.svelte";
  const totalSeconds = 3;
  let secondLeft = totalSeconds;
  let isRunning = false;
  //let width = 0;
  $: progress = ((totalSeconds - secondLeft) / totalSeconds) * 100;

  const dispatch = createEventDispatcher();
  function startTimer() {
    const timer = setInterval(() => {
      isRunning = true;
      secondLeft -= 1;
      //width += 33;
      if (secondLeft == 0) {
        isRunning = false;
        clearInterval(timer);
        secondLeft = totalSeconds;
        dispatch("end", "end timer");
        //width = 0;
      }
    }, 1000);
  }
</script>

<div bp="grid">
  <h2 bp="offset-5@md 4@md 12@sm">Seconds Left:{secondLeft}</h2>
</div>

<Progressbar {progress} />

<div bp="grid">
  <button
    disabled={isRunning}
    on:click={startTimer}
    bp="offset-5@md 4@md 12@sm"
    class="start"
    type="button">Start Washing</button
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

  .start[disabled] {
    background-color: grey;
    cursor: not-allowed;
  }
</style>
