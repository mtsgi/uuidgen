<script>
  import Generator from './lib/Generator.svelte';

  let isDark = false;
  const toggleDark = () => {
    isDark = !isDark;
  };
</script>

<main class:dark={isDark}>
  <h1>UUID Generator</h1>

  <Generator />

  <img
    on:click={toggleDark}
    src="/dark_theme.png"
    alt="Dark"
  />
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
    min-height: 100vh;
    box-sizing: border-box;
    background: var(--bg);
    color: var(--text);
    transition: var(--transition);

    --transition: all 0.25s ease;
    --bg: #ffffff;
    --border: #eeeeee;
    --text: #505050;
    --theme: #4987c0;
    --sub: #bcdeff;
  }

  main.dark {
    --bg: #303040;
    --border: #606070;
    --text: #ffffff;
    --theme: #9dccf8;
    --sub: #38495a;
  }

  main.dark :global(img) {
    filter: brightness(10);
  }

  h1 {
    color: var(--theme);
    font-size: 2.5rem;
    font-weight: 100;
    line-height: 1.1;
    margin: 0 0 2rem 0;
  }

  img {
    opacity: 0.6;
    cursor: pointer;
    height: 32px;
    transition: var(--transition);
  }

  @media (min-width: 480px) {
    h1 {
      font-size: 3rem;
    }
  }
</style>
