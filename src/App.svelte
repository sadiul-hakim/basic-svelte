<script>
  import Form from "./Form.svelte";

  let showContent = false;
  let names = ["Hakim", "Ashik", "Lamat"];
  let name = "Hakim";
  let heading = "<h2>Test Heading.</h2>";
  let disabled = true;
  let underline = "underline";
  let isUnderline = true;
  let promoted = true;

  let count = 0;

  function toggle(e) {
    showContent = !showContent;
  }
  function handleClick(event, num) {
    count += num;
  }
</script>

<main>
  <h1>Hello {name}!</h1>
  <button id="showButton" on:click={toggle}>show</button>

  {#if showContent}
    <button on:click={(event) => handleClick(event, 2)}>Add</button>
    <p>{count}</p>

    <p class={underline}>
      Hakim, A Java Spring Boot Developer, is learning Svelte for the UI of his
      backend program.
    </p>
    <p class={isUnderline ? "underline" : ""}>
      Hakim, A Java Spring Boot Developer, is learning Svelte for the UI of his
      backend program.
    </p>
    <p class:underline={isUnderline}>Underline</p>
    <p class:promoted>Promoted</p>
    {@html heading}
    <button {disabled}>Click</button>
    <!-- {:else if condition} -->
    {#each names as name, index (index)}
      <p>{index + 1}.{name}</p>
    {/each}
  {:else}
    <Form />
  {/if}
</main>

<style>
  .promoted {
    font-style: italic;
  }
  .underline {
    text-decoration: underline;
  }
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
