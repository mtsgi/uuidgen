<script>
  import Uuid from "./Uuid.svelte";

  let uuids = []
  const generate = () => {
    try {
      // @ts-ignore
      uuids = [...uuids, self.crypto.randomUUID()];
    } catch (error) {
      uuids = [...uuids, error];
    }
  }
</script>

<button on:click={generate}>
  Generate
</button>

<ul>
  {#each uuids as uuid}
    <Uuid {uuid} />
  {/each}
</ul>

<style>
  button {
    font-family: inherit;
    font-size: 1rem;
    padding: 1em;
    color: var(--theme);
    background-color: var(--sub);
    transition: var(--transition);
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
</style>
