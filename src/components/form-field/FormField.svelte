<script>
  export let label;
  export let error;
</script>

<style>

  .zui-formfield {
    position: relative;
    margin: 12px 0 24px 0;
  }

  .zui-formfield label {
    background: #fff;
    box-sizing: border-box;
    font-weight: bold;
    position: relative;
    line-height: 1em;
    margin-top: 0;
    padding: 0 4px;
    font-size: 0.9em;
    margin-left: 4px;
    margin-bottom: -1em;
    z-index: 2;
    width: fit-content;
  }

  .zui-formfield-error {
    position: absolute;
    bottom: -1.2em;
    left: 8px;
    color: var(--warn-color);
  }

</style>

<div class="zui-formfield" class:error>
  {#if label}
    <label>{label}</label>
  {/if}
  <slot></slot>
  {#if error}
    <small class="zui-formfield-error">{error}</small>
  {/if}
</div>