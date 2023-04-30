<script lang="ts">
  import { animate, scroll } from "motion";
  import { onMount } from "svelte";

  onMount(() => {
    scroll(animate(".progress", { strokeDasharray: ["0,1", "1,1"] }));
  });
</script>

<body>
  <h1>Page progress demo</h1>
  <svg width="50" height="50" viewBox="0 0 100 100">
    <circle cx="50" cy="50" r="30" pathLength="1" class="bg" />
    <circle cx="50" cy="50" r="30" pathLength="1" class="progress" />
  </svg>
  <article>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam ac
      rhoncus quam.
    </p>
    <p>
      Fringilla quam urna. Cras turpis elit, euismod eget ligula quis, imperdiet
      sagittis justo. In viverra fermentum ex ac vestibulum. Aliquam eleifend
      nunc a luctus porta. Mauris laoreet augue ut felis blandit, at iaculis
      odio ultrices. Nulla facilisi. Vestibulum cursus ipsum tellus, eu
      tincidunt neque tincidunt a.
    </p>
    <h2>Sub-header</h2>
    <p>
      In eget sodales arcu, consectetur efficitur metus. Duis efficitur
      tincidunt odio, sit amet laoreet massa fringilla eu.
    </p>
    <p>
      Pellentesque id lacus pulvinar elit pulvinar pretium ac non urna. Mauris
      id mauris vel arcu commodo venenatis. Aliquam eu risus arcu. Proin sit
      amet lacus mollis, semper massa ut, rutrum mi.
    </p>
    <p>Sed sem nisi, luctus consequat ligula in, congue sodales nisl.</p>
    <p>
      Vestibulum bibendum at erat sit amet pulvinar. Pellentesque pharetra leo
      vitae tristique rutrum. Donec ut volutpat ante, ut suscipit leo.
    </p>
    <h2>Sub-header</h2>
    <p>
      Maecenas quis elementum nulla, in lacinia nisl. Ut rutrum fringilla
      aliquet. Pellentesque auctor vehicula malesuada. Aliquam id feugiat sem,
      sit amet tempor nulla. Quisque fermentum felis faucibus, vehicula metus
      ac, interdum nibh. Curabitur vitae convallis ligula. Integer ac enim vel
      felis pharetra laoreet. Interdum et malesuada fames ac ante ipsum primis
      in faucibus. Pellentesque hendrerit ac augue quis pretium.
    </p>
    <p>
      Morbi ut scelerisque nibh. Integer auctor, massa non dictum tristique,
      elit metus efficitur elit, ac pretium sapien nisl nec ante. In et ex
      ultricies, mollis mi in, euismod dolor.
    </p>
    <p>Quisque convallis ligula non magna efficitur tincidunt.</p>
    <p>
      Pellentesque id lacus pulvinar elit pulvinar pretium ac non urna. Mauris
      id mauris vel arcu commodo venenatis. Aliquam eu risus arcu. Proin sit
      amet lacus mollis, semper massa ut, rutrum mi.
    </p>
    <p>Sed sem nisi, luctus consequat ligula in, congue sodales nisl.</p>
    <p>
      Vestibulum bibendum at erat sit amet pulvinar. Pellentesque pharetra leo
      vitae tristique rutrum. Donec ut volutpat ante, ut suscipit leo.
    </p>
    <h2>Sub-header</h2>
    <p>
      Maecenas quis elementum nulla, in lacinia nisl. Ut rutrum fringilla
      aliquet. Pellentesque auctor vehicula malesuada. Aliquam id feugiat sem,
      sit amet tempor nulla. Quisque fermentum felis faucibus, vehicula metus
      ac, interdum nibh. Curabitur vitae convallis ligula. Integer ac enim vel
      felis pharetra laoreet. Interdum et malesuada fames ac ante ipsum primis
      in faucibus. Pellentesque hendrerit ac augue quis pretium.
    </p>
    <p>
      Morbi ut scelerisque nibh. Integer auctor, massa non dictum tristique,
      elit metus efficitur elit, ac pretium sapien nisl nec ante. In et ex
      ultricies, mollis mi in, euismod dolor.
    </p>
    <p>Quisque convallis ligula non magna efficitur tincidunt.</p>
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

    --background: var(--black);
    --foreground: var(--white);
    --primary: var(--yellow);
    --secondary: var(--strong-blue);
    --success: var(--green);
    --error: var(--red);

    background: var(--black);
    color: var(--white);
    padding-bottom: 100px;
    letter-spacing: -0.3px;
  }

  * {
    font-family: Inter, sans-serif;
    -webkit-font-smoothing: antialiased;
  }

  h1 {
    font-size: 36px;
    font-weight: 700;
    letter-spacing: -1px;
    line-height: 1.2;
    text-align: center;
    margin: 100px 0;
  }

  h2 {
    font-weight: 400;
    margin: 50px 0 10px;
  }

  p {
    margin: 0 0 30px 0;
  }

  article {
    max-width: 500px;
    line-height: 1.6;
    margin: auto;
  }

  svg {
    position: fixed;
    top: 20px;
    left: 20px;
    transform: rotate(-90deg);
  }

  circle {
    stroke-dashoffset: 0;
    stroke-width: 15%;
    fill: none;
  }

  .bg {
    stroke: var(--feint);
  }

  .progress {
    stroke: var(--splash);
    stroke-dasharray: 0, 1;
  }
</style>
