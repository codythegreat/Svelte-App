<script>
  import ArtCardContainer from "./lib/components/ArtCardContainer.svelte";

  let imageSets = [
    [
      {
        src: "image3.png",
        alt: "native american man standing atop a cliff with an eagle on his shoulder. pacific northwest. washington. --v 4 --ar 3:2 --q 2",
        caption: "native american man standing atop a cliff with an eagle on his shoulder. pacific northwest. washington. --v 4 --ar 3:2 --q 2",
      }
    ],
    [
      {
        src: "image4.png",
        alt: "A calico cat surfing purple waves inspired by Katsushika Hokusai, sunset, beautiful, --v 4 --q 2 --ar 3:2",
        caption: "A calico cat surfing purple waves inspired by Katsushika Hokusai, sunset, beautiful, --v 4 --q 2 --ar 3:2",
      }
    ],
    [
      {
        src: "image5.png",
        alt: "wheres waldo, layered paper art, diorama --v 4 --q 2 --ar 1:1",
        caption: "wheres waldo, layered paper art, diorama --v 4 --q 2 --ar 1:1",
      }
    ],
    [
      {
        src: "image6.png",
        alt: "character concept for an adventurer dog, backpack, goggles, super cute, 2d --v 4 --q 2 --ar 1:1",
        caption: "character concept for an adventurer dog, backpack, goggles, super cute, 2d --v 4 --q 2 --ar 1:1",
      },
      {
        src: "image7.png",
        alt: "character concept for an adventurer dog, backpack, goggles, super cute, 2d --v 4 --q 2 --ar 1:1",
        caption: "character concept for an adventurer dog, backpack, goggles, super cute, 2d --v 4 --q 2 --ar 1:1",
      },
      {
        src: "image8.png",
        alt: "character concept for an adventurer dog, backpack, goggles, super cute, 2d --v 4 --q 2 --ar 1:1",
        caption: "character concept for an adventurer dog, backpack, goggles, super cute, 2d --v 4 --q 2 --ar 1:1",
      },
    ],
  ];
</script>



<main>
    <ArtCardContainer {imageSets}></ArtCardContainer>
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
