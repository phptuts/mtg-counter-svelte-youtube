<script>
  export let score = 20;
  export let won = false;
  export let winningText = "Red Won";
  export let fontColor = "#AA0000";
  export let isPlaying = true;
</script>

<style>
  div {
    flex-grow: 1;
  }
  .plus {
    background-color: seagreen;
  }
  .minus {
    background-color: brown;
  }
  button {
    font-size: 20px;
    border-radius: 3px;
    width: 40px;
    color: white;
    font-family: monospace;
    font-weight: bold;
  }
  button[disabled] {
    background-color: gray;
    cursor: not-allowed;
  }
</style>

<div style="color: {fontColor}">
  <h2>{score}</h2>
  <button disabled={!isPlaying} class="minus">-</button>
  <button disabled={!isPlaying} class="plus">+</button>
  {#if won}
    <h2>{winningText}</h2>
  {/if}
</div>
