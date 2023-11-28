<script>
	import Button from '../components/Button.svelte';

	import { BgSport, BgId } from '../stores';
	import football1 from '../images/football/football-1.jpg';
	import football2 from '../images/football/football-2.jpg';
	import football3 from '../images/football/football-3.jpg';
	import football4 from '../images/football/football-4.jpg';

	import basketball1 from '../images/basketball/basketball-1.jpg';
	import basketball2 from '../images/basketball/basketball-2.jpg';
	import basketball3 from '../images/basketball/basketball-3.jpg';
	import basketball4 from '../images/basketball/basketball-4.jpg';

	import defaultBg from '../images/default/default-1.jpg';

	const sports = ['Baseball', 'Basketball', 'Football', 'Hockey'];

	let imageSet = [defaultBg];
	let footballImages = [football1, football2, football3, football4];
	let basketballImages = [basketball1, basketball2, basketball3, basketball4];

	function ImageSetSelect() {
		let sportChoice = $BgSport;

		if (sportChoice === 'Football') {
			imageSet = footballImages;
		} else if (sportChoice === 'Basketball') {
			imageSet = basketballImages;
		} else {
			imageSet = [];
		}
	}
	let selectedSport = '';
	let isDisabled = true;

	function getRandomNumber() {
		let number = Math.floor(Math.random() * 3);
		BgId.set(number);
		BgSport.set(selectedSport);
	}
</script>

<div class="bg">
	<div class="filter"></div>
	<img class="img" src={imageSet[$BgId]} alt="random background" />
</div>
<div class="wrapper_page">
	<h1 class="title">Not Gambling</h1>

	<h3 class="subtitle">
		<label for="sportDropdown">Select your sport</label>
	</h3>

	<div class="wrapper_dropdown">
		<select
			name="sportDropdown"
			id="sportDropdown"
			bind:value={selectedSport}
			on:change={() => {
				isDisabled = false;
				getRandomNumber();
				ImageSetSelect();
			}}
		>
			<option value="" selected disabled hidden> Choose Here</option>

			{#each sports as sport}
				<option value={sport}>{sport}</option>
			{/each}
		</select>
		<Button id="loginBtn" disabled={isDisabled} target={selectedSport} text="Go!"></Button>
	</div>
</div>

<style>
	.filter {
		background: linear-gradient(to bottom, transparent, rgb(31, 31, 31) 95%);
		position: absolute;
		top: 0;
		left: 0;
		bottom: 0;
		min-height: 100%;
		width: 100%;
		z-index: -1;
		backdrop-filter: sepia(30%) blur(1px);
		pointer-events: none;
	}
	.bg {
		position: absolute;
		min-height: 100%;
		width: 100%;
		top: 0;
		left: 0;
		z-index: -2;
	}

	.img {
		position: absolute;
		min-height: 100%;
		width: 100%;
		z-index: inherit;
		object-fit: cover;
		pointer-events: none;
	}

	.wrapper_page {
		margin-top: 30vh;
		padding: 3em;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		backdrop-filter: blur(15px);
	}

	.title,
	.subtitle,
	.wrapper_dropdown {
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.title {
		font-size: 3rem;
		line-height: 1em;
		color: white;
		text-shadow:
			10px 10px black,
			-10px -10px black;
	}

	.subtitle {
		color: white;
		text-shadow: 3px 3px black;
	}

	select,
	option {
		font-family: inherit;
		font-size: 1.25rem;
		padding: 0.5em 1em;
		border: 5px solid black;
		box-shadow: 5px 5px 0px black;
		margin-right: 0.75em;
	}

	@media (min-width < 500px) {
		.title,
		.subtitle,
		.wrapper_dropdown {
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: center;
		}
	}
</style>
