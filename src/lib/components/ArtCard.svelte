<script>
// @ts-nocheck

  import ImgCountBubble from "./ImgCountBubble.svelte";
  import ImageViewer from "./ImageViewer.svelte";

  export let images = [];

  let showCaption = false;
  let showImageViewer = false;

  function showText() {
    showCaption = true;
  }

  function hideText() {
    showCaption = false;
  }

  function showImage() {
    showImageViewer = true;
  }

  function hideImage() {
    showImageViewer = false;
  }

  function handleKeydown(event) {
    if (event.key === "Escape") {
      hideImage();
      hideText();
    }
  }

  function copyCaption() {
    // get the text of the image-caption element
    let captionText = document.querySelector(".image-caption").innerText;

    // create a temporary textarea element
    let tempTextArea = document.createElement("textarea");
    tempTextArea.value = captionText;
    document.body.appendChild(tempTextArea);

    // select the text in the textarea
    tempTextArea.select();

    // copy the selected text
    document.execCommand("copy");

    // remove the textarea element
    document.body.removeChild(tempTextArea);
  }
</script>

<svelte:window on:keydown={handleKeydown}/>
<!-- svelte-ignore a11y-click-events-have-key-events -->
<div class="artcard" on:mouseenter={showText} on:mouseleave={hideText}>
  <img src={images[0].src} alt={images[0].alt} class="artcard-img" on:click={showImage}/>
  {#if showCaption}
    <div class="artcard-text">
      <span class="image-caption">{images[0].caption}</span>
      <span class="copy-text" on:click={copyCaption}>copy</span>
    </div>
  {/if}
  {#if showImageViewer}
    <ImageViewer {images}></ImageViewer>
  {/if}
  <ImgCountBubble count={images.length}></ImgCountBubble>
</div>

<style>
  .artcard {
    width: 256px;
    height: 256px;
    border-radius: 8px;
    background-size: cover;
    background-position: center;
    position: relative;
  }
  @media (max-width: 768px) {
    .artcard {
      flex: 50%;
    }
  }

  @media (min-width: 768px) {
    .artcard {
      margin: 25px;
    }
  }

  .artcard .artcard-img {
    cursor: pointer;
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: filter 0.5s ease-in-out, background 0.5s ease-in-out;
  }

  .artcard:hover .artcard-img {
    filter: blur(3px) brightness(60%);
    background: rgba(0, 0, 0, 0.25);
  }

  .artcard-text {
    position: absolute;
    left: -16px;
    right: -16px;
    top: 50%;
    transform: translateY(-50%);
    padding: 16px;
    background: rgba(255, 255, 255, 0.8);
    color: #333;
    font-size: 1.2rem;
    font-weight: bold;
  }

  .copy-text {
    cursor: pointer;
    position: absolute;
    bottom: 0;
    left: 0;
    font-size: 12px;
  }

  .copy-text:hover {
    text-decoration: underline;
  }
</style>