<script>
  let uuids = []
  const generate = () => {
    // @ts-ignore
    uuids = [...uuids, self.crypto.randomUUID()];
  }
</script>

<button on:click={generate}>
  Generate
</button>

<ul>
  {#each uuids as uuid}
    <li>{uuid}</li>
  {/each}
</ul>

<style>
  button {
    font-family: inherit;
    font-size: 1rem;
    padding: 1em;
    color: var(--theme);
    background-color: var(--sub);
    border-radius: 8px;
    border: 2px solid transparent;
    outline: none;
    cursor: pointer;
    margin: 0 0 1rem 0;
  }

  button:active {
    border: 2px solid var(--theme);
  }

  ul {
    padding: 0;
    list-style: none;
  }

  li {
    margin: 0 0 0.5rem 0;
  }
</style>
