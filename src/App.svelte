<script>
  import ArtCardContainer from "./lib/components/ArtCardContainer.svelte";
  import Nav from "./lib/components/Nav.svelte";

  import { filteredImages } from './lib/data/store.js';
  console.log(filteredImages);

  let images = []; // declare a local variable to hold the value of the filteredImages store

  filteredImages.subscribe(value => {
    images = value; // update the local variable with the latest value of the filteredImages store
  });


  console.log(images);
</script>



<main>
    <Nav></Nav>
    <ArtCardContainer imageSets={images}></ArtCardContainer>
</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
</style>
