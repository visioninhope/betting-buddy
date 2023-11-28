<script>
	export let name = '';
	export let id = '';
	export let inputs = [''];
</script>

<select {name} {id}>
	<option value="" selected disabled hidden> Choose Here</option>

	{#each inputs as input}
		<option value={input}>{input}</option>
	{/each}
</select>
