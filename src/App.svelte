<script>
  import { onMount } from "svelte";
  import Button from "./Button";

  let joke = "";

  onMount(fetchNewJoke);

  async function fetchJoke() {
    const resp = await fetch("https://api.chucknorris.io/jokes/random");
    return resp.json();
  }

  async function fetchNewJoke() {
    joke = "";
    joke = await fetchJoke();
  }
</script>

{#if joke === ''}
  <p>Loading</p>
{:else}
  <p>{joke.value}</p>
  <Button on:click={fetchNewJoke}>Fetch New Joke</Button>
{/if}
