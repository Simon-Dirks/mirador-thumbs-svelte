<script lang="ts">
  import { onMount } from "svelte";

  const manifestUrl =
    "https://iiif.io/api/cookbook/recipe/0001-mvm-image/manifest.json";

  const config = {
    id: "mirador",
    windows: [
      {
        manifestId: manifestUrl,
      },
    ],
  };

  onMount(async () => {
    // @ts-ignore
    const Mirador = (await import("mirador/dist/es/src/index")).default;
    Mirador.viewer(config);
  });
</script>

<div id="mirador"></div>

<style>
  #mirador {
    width: 100vw;
    height: 100vh;
  }
</style>
