<script>
	let date = new Date();
	let currentYear = date.getFullYear();
</script>

<svelte:head>
	<title>Sports App Test</title>
</svelte:head>

<slot />

<footer>
	<p>Howdy we did it</p>
	<p>Copyright {currentYear}</p>
</footer>

<style global>
	:root {
		font-family: 'Poppins', sans-serif;
	}
</style>
