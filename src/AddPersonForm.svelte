<script>
    import { createEventDispatcher } from 'svelte';

    let dispatch = createEventDispatcher();

    let name;
    let color;
    let age;
    let skills = [];

    const handleSubmit = () => {
        const person = {
            name,
            color,
            age,
            skills,
            id: Math.random()
        }
        dispatch('addPerson', person)
    }
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="number" placeholder="age" bind:value={age}>
    <label>Skills:</label>
    <input type="checkbox" bind:group={skills} value="svelte">svelte<br />
    <input type="checkbox" bind:group={skills} value="node">node<br />
    <input type="checkbox" bind:group={skills} value="react">react<br />
    <label>Color:</label>
    <select bind:value={color}>
        <option value="red">Red</option>
        <option value="blue">Blue</option>
        <option value="purple">Purple</option>
        <option value="yellow">Yellow</option>
    </select>
    <button>Add</button>
</form>

<style>

</style>
