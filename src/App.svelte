<script>
	let name = 'Yoshi';
	let beltColor = 'black'
	const handleClick = () => {
	    beltColor = 'orange'
	}

	const handeChangeEvent = (e) => {
	    beltColor = e.target.value
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<p style="color: {beltColor}">{beltColor} belt</p>
	<button on:click={handleClick}>Update belt colour</button>
<!--	<input type="text" on:input={(e) => handeChangeEvent(e)} value="{beltColor}">-->
	<input type="text" bind:value={beltColor}>
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
