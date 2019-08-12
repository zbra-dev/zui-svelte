<script>
	import {
		Button,
		ToggleButton,
		Rating,
	} from './components';

	$: clicks = 0;
	$: disabled = false;
</script>

<h3>Toggle Button</h3>
<ToggleButton on={true} />

<h3>Rating</h3>
<Rating value={2} />

<h3>Button</h3>
<strong>Clicks: {clicks}</strong><br>
<Button buttonStyle="primary" {disabled} on:click={() => clicks++}>Primary style</Button>
<Button buttonStyle="outline" {disabled} on:click={() => clicks++}>Outline style</Button>
<Button buttonStyle="clear" {disabled} on:click={() => clicks++}>Clear style</Button>
<Button buttonStyle="warn" {disabled} on:click={() => clicks++}>Warn style</Button>
<Button {disabled} expand on:click={() => clicks++}>Expand</Button>
<h4><label><input type=checkbox bind:checked={disabled}>Disable buttons</label></h4>


