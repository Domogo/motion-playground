<script lang="ts">
  import { animate, stagger } from "motion";
  import { onMount } from "svelte";

  const offset = 0.09;
  onMount(() => {
    const segments = document.querySelectorAll(".segment");
    const numSegments = segments.length;

    animate(
      segments,
      { opacity: [0, 1, 0] },
      {
        offset: [0, 0.1, 1],
        duration: numSegments * offset,
        delay: stagger(offset),
        repeat: Infinity,
      }
    );
  });
</script>

<body>
  <svg xmlns="http://www.w3.org/2000/svg" width="200" height="200">
    <g class="segment">
      <path
        id="loading-path"
        d="M 94 25 C 94 21.686 96.686 19 100 19 L 100 19 C 103.314 19 106 21.686 106 25 L 106 50 C 106 53.314 103.314 56 100 56 L 100 56 C 96.686 56 94 53.314 94 50 Z"
      />
    </g>
    <g class="segment">
      <use
        href="#loading-path"
        style="transform: rotate(45deg); transform-origin: 100px 100px"
      />
    </g>
    <g class="segment">
      <use
        href="#loading-path"
        style="transform: rotate(90deg); transform-origin: 100px 100px"
      />
    </g>
    <g class="segment">
      <use
        href="#loading-path"
        style="transform: rotate(135deg); transform-origin: 100px 100px"
      />
    </g>
    <g class="segment">
      <use
        href="#loading-path"
        style="transform: rotate(180deg); transform-origin: 100px 100px"
      />
    </g>
    <g class="segment">
      <use
        href="#loading-path"
        style="transform: rotate(225deg); transform-origin: 100px 100px"
      />
    </g>
    <g class="segment">
      <use
        href="#loading-path"
        style="transform: rotate(270deg); transform-origin: 100px 100px"
      />
    </g>
    <g class="segment">
      <use
        href="#loading-path"
        style="transform: rotate(315deg); transform-origin: 100px 100px"
      />
    </g>
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

  .segment {
    opacity: 0;
    fill: #00ffdb;
  }
</style>
