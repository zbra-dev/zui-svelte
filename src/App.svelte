<script>
	import {
		Button,
		Input,
		FormField,
		Rating,
		ToggleButton,
	} from './components';

	$: clicks = 0;
	$: disabled = false;
	$: expand = false;
</script>

<h3>Toggle Button</h3>
<ToggleButton on={true} />

<h3>Rating</h3>
<Rating value={2} />

<label><input type=checkbox bind:checked={disabled}>Disable</label>
<label><input type=checkbox bind:checked={expand}>Expand</label>

<h3>Button</h3>
<strong>Clicks: {clicks}</strong><br>
<Button buttonStyle="primary" {disabled} {expand} on:click={() => clicks++}>Primary style</Button>
<Button buttonStyle="outline" {disabled} {expand} on:click={() => clicks++}>Outline style</Button>
<Button buttonStyle="clear" {disabled} {expand} on:click={() => clicks++}>Clear style</Button>
<Button buttonStyle="warn" {disabled} {expand} on:click={() => clicks++}>Warn style</Button>

<h3>Input</h3>
<Input value='320.50' type="number" prefix="R$" {disabled} {expand}/>
<Input {disabled} {expand}/>

<FormField label='FormField'>
	<Input type=text value="aldhfsjfhdl" {disabled} {expand}/>
</FormField>

<FormField label='FormField' error="Error message">
	<Input type=text value="aldhfsjfhdl" {disabled} {expand}/>
</FormField>
