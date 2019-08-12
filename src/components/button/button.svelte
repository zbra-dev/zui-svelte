<script>
  export let buttonStyle = 'primary';
  export let disabled = false;
  export let expand = false;
</script>

<style src='./button-style.scss'></style>

<button
  class={`button-style-${buttonStyle}`}
  class:expand
  {disabled}
  on:click>
  <slot></slot>
</button>
