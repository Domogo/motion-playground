<script lang="ts">
  import { animate, stagger } from "motion";
  import { onMount } from "svelte";

  onMount(() => {
    animate(
      ".box",
      {
        rotate: 90,
      },
      {
        duration: 0.5,
        repeat: 3,
        easing: "ease-in-out",
        direction: "alternate",
        delay: stagger(1),
      }
    );
  });
</script>

<body class="w-screen">
  <div class="flex flex-col gap-3">
    <div class="box" />
    <div class="box" />
    <div class="box" />
  </div>
</body>

<style>
  body {
    margin: 0;
    padding: 0;
    --white: #f5f5f5;
    --black: #0f1115;
    --yellow: #ffeb0e;
    --strong-blue: #0d63f8;
    --blue: #31a6fa;
    --green: #57eb64;
    --pink: #ff2965;
    --red: #ff1231;
    --splash: #00ffdb;
    --feint: rgba(133, 150, 193, 0.1);

    --background: var(--black);
    --foreground: var(--white);
    --primary: var(--yellow);
    --secondary: var(--strong-blue);
    --success: var(--green);
    --error: var(--red);

    background: var(--background);
    display: flex;
    justify-content: center;
    align-items: center;
    height: 90vh;
  }

  .box {
    width: 100px;
    height: 100px;
    border-radius: 10px;
    background-color: var(--splash);
  }
</style>
