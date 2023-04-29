<script lang="ts">
  import { timeline } from "motion";
  import { onMount } from "svelte";

  onMount(() => {
    /**
     * Remember to set the pathLength="1" SVG attribute on
     * the elements you want to draw. This makes it easy
     * to use the same animation logic for elements of a
     * different path length.
     */

    const draw = (progress: number) => ({
      // This property makes the line "draw" in when animated
      strokeDashoffset: 1 - progress,

      // Each line will be hidden until it starts drawing
      // to fix a bug in Safari where the line can be
      // partially visible even when progress is at 0
      visibility: "visible",
    });

    timeline([
      ["circle", draw(1), { duration: 0.8, delay: 1 }],
      ["path", draw(1), { duration: 0.6, at: "-0.2" }],
    ]);
  });
</script>

<body>
  <svg xmlns="http://www.w3.org/2000/svg" width="200" height="200">
    <circle cx="100" cy="100" r="80" pathLength="1" />
    <path d="M 54 107.5 L 88 138.5 L 144.5 67.5" pathLength="1" />
  </svg>
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

  circle,
  path {
    fill: transparent;
    stroke: #57eb64;
    stroke-width: 6px;
    stroke-dasharray: 1;
    stroke-dashoffset: 1;
    stroke-linecap: round;
    stroke-linejoin: round;
    visibility: hidden;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
  }

  circle {
    transform-origin: 100px 100px;
    transform: rotate(-90deg);
  }
</style>
