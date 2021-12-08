<script>
  import HowTo from "./HowTo.svelte";
  import Timer from "./Timer.svelte";
  let audio;
  function timerEnds(e) {
    audio.play();
  }
</script>

<h1>Hand Washing App</h1>

<Timer on:end={timerEnds} />

<HowTo />

<h3>
  <a
    href="https://www.who.int/teams/integrated-health-services/infection-prevention-control"
    >Picture Source</a
  >
  <a href="https://freesound.org/">Sound Source</a>
</h3>

<audio bind:this={audio}>
  <source src="sound.wav" />
</audio>

<style>
  h1,
  h3 {
    text-align: center;
  }
</style>
