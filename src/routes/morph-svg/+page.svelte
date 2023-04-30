<script>
  // @ts-nocheck
  import { onMount } from "svelte";
  import { animate } from "motion";
  import { interpolate } from "flubber";
  import { paths } from "./paths";

  let path = null;
  let currentPath = paths.star;
  const transition = { duration: 0.5 };

  onMount(() => {
    path = document.querySelector("path");
  });

  function togglePath() {
    currentPath = currentPath === paths.star ? paths.heart : paths.star;

    const mixPaths = interpolate(path.getAttribute("d"), currentPath.d, {
      maxSegmentLength: 0.1,
    });

    animate(path, { fill: currentPath.color }, transition);
    animate(
      (progress) => path.setAttribute("d", mixPaths(progress)),
      transition
    );
  }
</script>

<body>
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div on:click={togglePath}>
    <svg width="200" height="200" viewBox="0 0 400 400">
      <g transform="translate(10 10) scale(17 17)">
        <path fill={currentPath.color} d={currentPath.d} />
      </g>
    </svg>
  </div>
</body>

<style>
  body {
    background: #0f1115;
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>
