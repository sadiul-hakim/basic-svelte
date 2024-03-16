<script>
  let name = "Hakim";
  let heading = "<h2>Test Heading.</h2>";
</script>

<main>
  <h1>Hello {name}!</h1>
  <p>
    Hakim, A Java Spring Boot Developer, is learning Svelte for the UI of his
    backend program.
  </p>
  {@html heading}
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
