<script lang="ts">
    let name;
    let beltColour;
    let age;
    let fighting = false;
    let sneaking = false;
    let running = false;
    let handleSubmit = () => {
        console.log(name, beltColour, age, fighting, sneaking, running);
    };
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="text" placeholder="belt colour" bind:value={beltColour}>
    <input type="number" placeholder="age" bind:value={age}>
    <label>Skills:</label>
    <input type="checkbox" bind:checked={fighting}> fighting <br>
    <input type="checkbox" bind:checked={sneaking}> sneaking <br>
    <input type="checkbox" bind:checked={running}> running <br>
    <button>Add Person</button>
</form>
