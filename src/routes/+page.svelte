<script>
	import { BgSport, BgId } from '../stores';
	import football1 from '../images/football/football-1.jpg';
	import football2 from '../images/football/football-2.jpg';
	import football3 from '../images/football/football-3.jpg';
	import football4 from '../images/football/football-4.jpg';

	import basketball1 from '../images/basketball/basketball-1.jpg';
	import basketball2 from '../images/basketball/basketball-2.jpg';
	import basketball3 from '../images/basketball/basketball-3.jpg';
	import basketball4 from '../images/basketball/basketball-4.jpg';

	let imageSet = [''];
	let footballImages = [football1, football2, football3, football4];
	let basketballImages = [basketball1, basketball2, basketball3, basketball4];

	function ImageSetSelect() {
		let sportChoice = $BgSport;

		if (sportChoice === 'football') {
			imageSet = footballImages;
		} else if (sportChoice === 'basketball') {
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
		ImageSetSelect();
	}
</script>

<div class="bg">
	<div class="filter"></div>
	<img class="img" src={imageSet[$BgId]} alt="random background" />
</div>

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
		}}
	>
		<option value="" selected disabled hidden> Choose Here</option>
		<option value="basketball">Basketball</option>
		<option value="football">Football</option>
		<option value="hockey">Hockey</option>
		<option value="Soccer">Soccer</option>
	</select>

	<button id="loginBtn" disabled={isDisabled}><a href="./{selectedSport}">Go!</a></button>
</div>

<style>
	.filter {
		background: linear-gradient(to bottom, transparent, black 85%);
		position: absolute;
		top: 0;
		left: 0;
		height: 100%;
		width: 100%;
		z-index: -1;
		backdrop-filter: sepia(100%) blur(5px);
	}
	.bg {
		position: absolute;
		height: 100%;
		width: 100%;
		top: 0;
		left: 0;
		z-index: -2;
	}

	.img {
		position: absolute;
		height: 100%;
		width: 100%;
		z-index: inherit;
	}

	a {
		text-decoration: none;
		color: inherit;
	}

	button:disabled {
		color: grey;
	}

	.title,
	.subtitle,
	.wrapper_dropdown {
		display: flex;
		align-items: center;
		justify-content: center;
	}
</style>
