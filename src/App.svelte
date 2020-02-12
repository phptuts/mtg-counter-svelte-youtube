<script>
  import Player from "./Player.svelte";
  let redScore = 0;
  let blueScore = 0;
  $: blueWon = redScore <= 0 && blueScore > 0;
  $: redWon = blueScore <= 0 && redScore > 0;
  $: isPlaying = !blueWon && !redWon && redScore > 0 && blueScore > 0;

  function startGame() {
    redScore = 20;
    blueScore = 20;
  }

</script>

<style>
  main {
    width: 80%;
    padding: 20px;
    border: solid gray 1px;
    margin: 0 auto;
    background-color: wheat;
    margin: 10vh auto;
  }

  #player-container {
    display: flex;
  }

  button {
    display: block;
    width: 100%;
    margin-top: 20px;
    border: solid salmon 1px;
    background-color: sandybrown;
    color: rgb(61, 56, 56);
    font-size: 20px;
    border-radius: 3px;
  }
</style>

<main>
  <h1>Magic The Gathering Counter</h1>
  <section id="player-container">
    <Player
      score={redScore}
      winningText="Red Won"
      won={blueWon}
      fontColor="#AA0000"
      {isPlaying} />
    <Player
      fontColor="#0000AA"
      score={blueScore}
      winningText="Blue Won"
      won={redWon}
      {isPlaying} />
  </section>
  <button on:click={startGame}>Start Game</button>
</main>
