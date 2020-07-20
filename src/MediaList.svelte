<script>
  import Media from './Media.svelte';
  let promise = getMedias();

  async function getMedias() {
    const res = await fetch('https://api-test-six.vercel.app/api/media');
    const json = await res.json();
    return json;
  }
</script>

{#await promise}
  <p>...loading</p>
{:then data}
  {#each data as props}
    <Media {props} />
  {:else}
    <p>No Media Found</p>
  {/each}
{:catch error}
  <p>{error}</p>
{/await}
