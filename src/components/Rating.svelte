<script>
  export let value = 0;
  export let maxValue = 5;
</script>

{#each { length: maxValue } as _, i}
  <button on:click={e => value = i}>
    {i <= value ? '✓': '✗'}
  </button>
{/each}
