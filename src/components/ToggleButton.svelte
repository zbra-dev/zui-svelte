<script>
  export let on = false;

  function toggleOn() {
    on = !on;
  }
</script>

<button on:click={toggleOn}>{on ? 'On' : 'Off'}</button>