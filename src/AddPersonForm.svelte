<script lang="ts">
    let name;
    let beltColour;
    let age;
    // let fighting = false;
    // let sneaking = false;
    // let running = false;
    let skills;
    let handleSubmit = () => {
        console.log(name, beltColour, age, skills);
    };
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="number" placeholder="age" bind:value={age}>
    <label>Skills:</label>
    <label>
        <input type="radio" bind:group={skills} value="fighting">
        <span>fighting</span>
    </label>
    <input type="radio" bind:group={skills} value="sneaking"> sneaking <br>
    <input type="radio" bind:group={skills} value="running"> running <br>
    <label>Belt colour:</label>
    <select bind:value={beltColour}>
        <option value="black">black</option>
        <option value="orange">orange</option>
        <option value="brown">brown</option>
        <option value="white">white</option>
    </select>
    <button>Add Person</button>
</form>
