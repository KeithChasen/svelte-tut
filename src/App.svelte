<script>
	 let name = 'Kostya';
	 let profession = '';
	 const handleClick = () => {
		 name = 'Kostya Chernysh'
	 }
	 const setProfession = () => {
		 profession = 'web dev'
	 }
	 const handleInput = (e) => {
		 profession = e.target.value;
	 }
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Profession: {profession}</p>
	<button on:click={handleClick}>Update</button>
	<button on:click={setProfession}>Set Profession</button>
	<input type="text" on:input={handleInput} value={profession}>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>