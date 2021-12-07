<script>
    let name;
    let color;
    let age;
    let svelte = false;
    let node = false;
    let react = false;

    const handleSubmit = () => {
        console.log(name, color, age, svelte, node, react)
    }
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="text" placeholder="color" bind:value={color}>
    <input type="number" placeholder="age" bind:value={age}>
    <label>Skills:</label>
    <input type="checkbox" bind:checked={svelte}>svelte<br />
    <input type="checkbox" bind:checked={node}>node<br />
    <input type="checkbox" bind:checked={react}>react<br />
    <button>Add</button>
</form>

<style>

</style>
