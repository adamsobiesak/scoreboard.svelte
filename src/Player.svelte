<script>
  export let name;
  export let points;
  let showControls = false;

  const addPoints = () => (points += 1);
  const removePoints = () => (points -= 1);
  const toggleControls = () => (showControls = !showControls);
</script>

<style>
  h1 {
    color: #204f6e;
  }
</style>

<div class="card">
  <h1>
     {name}
    <button class="btn btn-sm" on:click={toggleControls}>
      {#if showControls}-{:else}+{/if}
    </button>
  </h1>
  <h3>points: {points}</h3>
  {#if showControls}
    <button class="btn" on:click={addPoints}>+1</button>
    <button class="btn btn-dark" on:click={removePoints}>-1</button>
    <input type="number" bind:value={points} />
  {/if}
</div>
