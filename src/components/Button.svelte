<script>
	export let id = '';
	export let disabled = true;
	export let text = '';
	export let target = '';
</script>

<a href="./{target}">
	<button {id} {disabled} type="button">
		{text}
	</button>
</a>

<style>
	a {
		text-decoration: none;
	}

	button:disabled {
		color: rgb(148, 146, 146);
		background-color: grey;
	}

	button {
		background-color: rgb(1, 194, 194);
		color: black;
		border: 5px solid black;
		padding: 0.5em 1.5em;
		box-shadow: 5px 5px 0px black;
		margin-right: 0.75em;
		transition-duration: 500ms;
		cursor: pointer;
		font-family: inherit;
		color: white;
		font-weight: bolder;
		font-size: 1.2rem;
	}

	button:hover {
		transform: scale(1.05);
		translate: -1px -3px;
		box-shadow: 5px 10px 0px black;
	}
</style>
