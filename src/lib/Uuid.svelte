<script>
  import { slide } from "svelte/transition";
  export let uuid;

  let input;
  const copy = () => {
    input.select();
    document.execCommand("copy");
  }
</script>

<li transition:slide>
  <input value={uuid} readonly bind:this={input} />
  <img on:click={copy} src="/clipboard.png" alt="Copy" />
</li>

<style>
  li {
    padding: 0.5em;
    border-top:1px solid #eee;
    display: flex;
    align-items: center;
  }

  li > input {
    all: inherit;
    border: none;
    padding: 0;
    flex-grow: 1;
    word-break: break-all;
  }

  li > img {
    padding: 0 0.25rem;
    width: 1.5rem;
    height: 1.5rem;
    cursor: pointer;
    opacity: 0.5;
  }

  li > img:hover {
    opacity: 1;
  }
</style>
