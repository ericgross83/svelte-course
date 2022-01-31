<script lang="ts">
    let name;
    let beltColour;
    let age;
    // let fighting = false;
    // let sneaking = false;
    // let running = false;
    let skills = [];
    let handleSubmit = () => {
        console.log(name, beltColour, age, skills);
    };
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="text" placeholder="belt colour" bind:value={beltColour}>
    <input type="number" placeholder="age" bind:value={age}>
    <label>Skills:</label>
    <input type="checkbox" bind:group={skills} value="fighting"> fighting <br>
    <input type="checkbox" bind:group={skills} value="sneaking"> sneaking <br>
    <input type="checkbox" bind:group={skills} value="running"> running <br>
    <button>Add Person</button>
</form>
