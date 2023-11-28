<script>
	let date = new Date();
	let currentYear = date.getFullYear();
</script>

<svelte:head>
	<title>Sports App Testing</title>
</svelte:head>

<slot />

<footer>
	Copyright {currentYear}

	<a href="https://github.com/amersinger21/sports_data_app">Github</a>
</footer>

<style global>
	:root {
		font-family: 'Poppins', sans-serif;
		margin: 0;
		padding: 0;
	}

	footer {
		bottom: 0;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		color: white;
	}

	footer > a {
		color: aquamarine;
	}
</style>
