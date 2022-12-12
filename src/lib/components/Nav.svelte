<script>
  import { onMount } from 'svelte';
  import { filteredImages } from '../data/store.js';
  import images from '../data/imageData.json';

  let searchTerm = '';
  let placeholder = '';

  onMount(() => {
    filteredImages.set(images);
    const randomImage = images[Math.floor(Math.random() * images.length)];
    const words = randomImage[0].caption.split(' ');
    placeholder = words.slice(0, 5).join(' ') + (words.length > 5 ? '...' : '');
  });

  function handleSearch(event) {
    searchTerm = event.target.value;
    filteredImages.set(images.filter(image => image[0].caption.includes(searchTerm)));
  }
</script>

<nav>
  <div class="search">
    <input type="text" bind:value={searchTerm} {placeholder} on:input={handleSearch} />
  </div>
</nav>

<style>
  nav {
    height: 50px;
    background-color: #333;
  }

  .search {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
  }

  input[type="text"] {
    width: 300px;
    height: 30px;
    padding: 0 10px;
    border-radius: 5px;
    border: none;
    outline: none;
    background-color: #444;
    color: #ddd;
  }
</style>