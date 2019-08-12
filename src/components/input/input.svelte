<script>
  export let type='text';
  export let value = '';
  export let placeholder = 'Placeholder';
  export let label;
  export let disabled = false;
  export let expand = false;
  export let prefix;
  $: focused = false;

</script>
<style>
  .input-container {
    position: relative;
    display: flex;
    flex-direction: row;
    align-items: center;
    margin: 0.5em 0;
    border: 1px solid #999;
    border-radius: 4px;
    padding: 0 8px;
    background: #fff;
    white-space: nowrap;
    width: fit-content;
  }

  .input-container .prefix {
    margin-right: 6px;
  }

  .input-container.disabled .prefix {
    color: #666;
  }

  .input-container input {
    min-height: 40px;
    margin: 0;
    padding: 0;
    border: none;
    background: transparent;
  }

  .input-container input:focus {
    outline: none;
  }

  .input-container.expand {
    width: unset;
    flex: 1;
  }

  .input-container.expand input {
    flex: 1;
  }

  .input-container .outline {
    border-radius: 4px;
    pointer-events: none;
    position: absolute;
    bottom: -1px;
    left: -1px;
    right: -1px;
    top: -1px;
    transition: 160ms ease-out;
    opacity: 0;
    border: 1px solid var(--primary-color);
  }

  .input-container.focused .outline {
    transition-timing-function: ease-in;
    opacity: 1;
    border: 2px solid var(--primary-color);
  }

  .input-container.disabled {
    opacity: 0.7;
  }

  .input-container.disabled .outline {
    border-color: #eee;
  }

  .input-container.disabled input[disabled] {
    border-color: #ccc;
    color: #666;
  }
</style>

<div class='input-container' class:focused class:disabled class:expand>

  {#if prefix}
    <span class="prefix">{prefix}</span>
  {/if}

  <input {type} {value} {placeholder} {disabled}
    on:focus={() => focused = true}
    on:blur={() => focused = false}
  >
  <div class="outline"></div>
</div>
