<script>
  import Navbar from "./Navbar.svelte";
  import Player from "./Player.svelte";

  let players = [
    { name: "Jan Janowski", points: 33 },
    { name: "Harrison Ford", points: 55 },
    { name: "Indiana Jones", points: 72 }
  ];
</script>

<Navbar />
<div class="container">
  {#if players.length === 0}
    <p>No players</p>
  {:else}
    {#each players as player}
      <Player name={player.name} points={player.points} />
    {/each}
  {/if}
</div>
