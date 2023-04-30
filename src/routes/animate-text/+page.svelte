<script lang="ts">
  import { onMount } from "svelte";
  import { animate } from "motion";

  let counter = 0;

  onMount(() => {
    animate((progress) => (counter = Math.round(progress * 100)), {
      duration: 2,
      easing: "ease-out",
      delay: 1,
    });
  });
</script>

<body>
  <h1>{counter}</h1>
</body>

<style>
  body {
    background: #0f1115;
    display: flex;
    align-items: center;
    justify-content: center;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
  }

  h1 {
    font-family: sans-serif;
    font-weight: bold;
    font-size: 16px;
    color: white;
  }
</style>
