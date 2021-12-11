<script>
  import Generator from './lib/Generator.svelte';
</script>

<main>
  <h1>UUID Generator</h1>

  <Generator />
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
      Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    line-height: 1.5;
  }

  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
    color: var(--text);

    --text: #505050;
    --theme: #4987c0;
    --sub: #bcdeff;
  }

  h1 {
    color: var(--theme);
    font-size: 2.5rem;
    font-weight: 100;
    line-height: 1.1;
    margin: 0 0 2rem 0;
  }

  @media (min-width: 480px) {
    h1 {
      font-size: 3rem;
    }
  }
</style>
