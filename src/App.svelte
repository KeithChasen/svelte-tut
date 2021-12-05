<script>
	 let people = [
		 { name: 'Jack', color: 'red', age: 35, id: 1 },
		 { name: 'John', color: 'blue', age: 23, id: 2 },
		 { name: 'Jane', color: 'yellow', age: 44, id: 3 },
	 ];
</script>

<main>
	{#each people as person (person.id)}
		<div>
			<h4>{person.name}</h4>
			<p style='color: {person.color}'>{person.age} years old</p>
		</div>
	{:else}
		<p>There's no one there</p>
	{/each}
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