<script lang="ts">
  import { animate, scroll } from "motion";
  import { onMount } from "svelte";

  onMount(() => {
    scroll(animate(".progress", { scaleX: [0, 1] }));

    const sections = document.querySelectorAll("section");
    sections.forEach((section) => {
      const header = section.querySelector("h2") as Element;
      scroll(animate(header, { y: [-400, 400] }), {
        target: header,
      });
    });
  });
</script>

<html lang="">
  <body>
    <section>
      <div>
        <img src="/images/public/1.jpeg" />
        <h2>#001</h2>
      </div>
    </section>
    <section>
      <div>
        <img src="/images/public/2.jpeg" />
        <h2>#002</h2>
      </div>
    </section>
    <section>
      <div>
        <img src="/images/public/3.jpeg" />
        <h2>#003</h2>
      </div>
    </section>
    <section>
      <div>
        <img src="/images/public/4.jpeg" />
        <h2>#004</h2>
      </div>
    </section>
    <section>
      <div>
        <img src="/images/public/5.jpeg" />
        <h2>#005</h2>
      </div>
    </section>
    <div class="progress" />
  </body>
</html>

<style>
  body {
    font-family: sans-serif;
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

    --background: var(--white);
    --foreground: var(--black);
    --primary: var(--yellow);
    --secondary: var(--strong-blue);
    --success: var(--green);
    --error: var(--red);

    background: var(--background);
    color: var(--foreground);

    padding: 0;
  }

  * {
    font-family: Inter, sans-serif;
  }

  html {
    scroll-snap-type: y mandatory;
  }

  h1 {
    font-weight: 400;
    text-align: center;
    margin: 100px 0;
  }

  h2 {
    margin: 0;
    color: var(--red);
    font-size: 50px;
    font-weight: 700;
    letter-spacing: -3px;
    line-height: 1.2;
    position: absolute;
    display: inline-block;
    top: calc(50% - 25px);
    left: calc(50% + 120px);
  }

  section {
    height: 100vh;
    scroll-snap-align: start;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
  }

  section > div {
    width: 300px;
    height: 400px;
    margin: 20px;
    background: var(--white);
    overflow: hidden;
  }

  img {
    width: 300px;
    height: 400px;
  }

  .progress {
    position: fixed;
    left: 0;
    right: 0;
    height: 5px;
    background: var(--red);
    bottom: 50px;
    transform: scaleX(0);
  }
</style>
