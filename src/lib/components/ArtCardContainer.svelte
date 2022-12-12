<script>
  import ArtCard from "./ArtCard.svelte";

  export let imageSets = [];
</script>

<div class="artcard-container">
  {#if imageSets.length === 0}
    <h2 id="no-images-found-text">No Images Found</h2>
  {:else}
    {#each imageSets as images}
      <ArtCard {images} />
    {/each}
  {/if}
</div>

<style>
  .artcard-container {
    width: 100%;
    background-color: #222;
    display: flex;
    flex-wrap: wrap;
    min-height: calc(100vh - 50px);
    align-content: flex-start;
  }

  #no-images-found-text {
    margin: 40vh auto;
    color: #bbb;
    font-size: 48px;
  }
</style>