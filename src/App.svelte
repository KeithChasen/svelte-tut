<script>
	import Modal from "./Modal.svelte";

	let showModal = false;

	 let people = [
		 { name: 'Jack', color: 'red', age: 35, id: 1 },
		 { name: 'John', color: 'blue', age: 23, id: 2 },
		 { name: 'Jane', color: 'yellow', age: 44, id: 3 },
	 ];

	 const handleClick = (id) => {
		 people = people.filter(person => person.id !== id)
	 }

	 const toggleModal = () => {
		 showModal = !showModal;
	 }
</script>

<Modal {showModal} on:click={toggleModal}>
	<h3>Add a new person</h3>
	<form>
		<input type="text" placeholder="name">
		<input type="text" placeholder="color">
		<button>Add</button>
	</form>
</Modal>
<main>
	<button on:click={toggleModal}>Open modal</button>
	{#each people as person (person.id)}
		<div>
			<h4>{person.name}</h4>
			{#if person.age > 25}
				<p style="background: {person.color}; width: 50%; margin: auto">Award</p>
			{:else}
				<p style="background: {person.color}; width: 25%; margin: auto; color: white">none</p>
			{/if}
			<p style='color: {person.color}'>{person.age} years old</p>
			<button on:click={() => handleClick(person.id)}>delete</button>
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