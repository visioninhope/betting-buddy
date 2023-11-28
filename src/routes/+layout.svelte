<script>
	let date = new Date();
	let currentYear = date.getFullYear();
</script>

<svelte:head>
	<title>Sports App Test</title>
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
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		color: white;
		height: 50px;
		position: absolute;
		bottom: 0;
		right: 0;
		left: 0;
	}

	footer > a {
		color: aquamarine;
	}
</style>
