<script>
  export let images = [];

  let currentImageIndex = 0;

  function goToPreviousImage() {
    currentImageIndex = currentImageIndex === 0 ? images.length - 1 : currentImageIndex - 1;
  }

  function goToNextImage() {
    currentImageIndex = currentImageIndex === images.length - 1 ? 0 : currentImageIndex + 1;
  }
</script>

<div class="image-viewer">
  {#if images.length > 0}
    <img src={images[currentImageIndex].src} alt={images[currentImageIndex].alt} class="image-viewer-img" />
    {#if images.length > 1}
      <div class="controls">
        <button on:click={goToPreviousImage}>Previous</button>
        <button on:click={goToNextImage}>Next</button>
      </div>
    {/if}
  {/if}
</div>

<style>
  .image-viewer {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.75);
    z-index: 99;
  }

  .image-viewer .image-viewer-img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    object-position: center;
  }

  .controls {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 48px;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 0 16px;
    background-color: rgba(0, 0, 0, 0.5);
  }

  .controls button {
    width: 32px;
    height: 32px;
    font-size: 24px;
    font-weight: bold;
    border: none;
    background-color: transparent;
    color: white;
    cursor: pointer;
  }
  .controls button:first-of-type {
    margin-right: 25px;
  }
  .controls button:not(first-of-type) {
    margin-left: 25px;
  }
</style>