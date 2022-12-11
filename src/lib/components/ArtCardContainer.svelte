<script>
  import ArtCard from "./ArtCard.svelte";

  export let imageSets = [];
</script>

<div class="artcard-container">
  {#each imageSets as images}
    <ArtCard {images} />
  {/each}
</div>

<style>
  .artcard-container {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
  }
</style>