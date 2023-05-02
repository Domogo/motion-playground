<script lang="ts">
  import { onMount } from "svelte";
  import { scroll, animate } from "motion";

  onMount(() => {
    const sectionDivs = document.querySelectorAll("section > div");
    sectionDivs.forEach((item) => {
      scroll(animate(item, { opacity: [0, 1, 1, 0] }), {
        target: item,
        offset: ["start end", "end end", "start start", "end start"],
      });
    });
  });
</script>

<body>
  <article>
    <section>
      <div><img src="/images/public/1.jpeg" /></div>
    </section>
    <section>
      <div><img src="/images/public/2.jpeg" /></div>
    </section>
    <section>
      <div><img src="/images/public/3.jpeg" /></div>
    </section>
    <section>
      <div><img src="/images/public/4.jpeg" /></div>
    </section>
    <section>
      <div><img src="/images/public/5.jpeg" /></div>
    </section>
  </article>
</body>

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
  }

  * {
    font-family: Inter, sans-serif;
  }

  h1 {
    font-weight: 400;
    text-align: center;
    margin: 100px 0;
  }

  h2 {
    margin: 50px 0 10px;
    color: var(--black);
    font-size: 48px;
  }

  section {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
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
</style>
