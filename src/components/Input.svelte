<script>
	let word;
	import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();
	function handleClick() {
		dispatch('search', word);
	}
</script>

<div id="container">
	<input type="text" bind:value={word} placeholder="Search for any word..." />
	<div>
		<button on:click={handleClick} class="fa-solid fa-search search" />
	</div>
</div>

<style>
	#container {
		margin-top: 2rem;
		display: flex;
		justify-content: center;
		align-items: center;
		background-color: whitesmoke;
		border-radius: 20px;
	}
	.search {
		background-color: var(--bg-light);
		border: 0;
		padding-right: 30px;
		background-color: whitesmoke;
		color: var(--color-purple);
	}
	input {
		background-color: transparent;
		width: 100%;
		height: 50px;
		padding-left: 20px;
		font-family: var(--font-serif);
		font-size: 17px;
		outline: 0;
		font-weight: bold;
		opacity: 0.5;
		border: 0;
	}
</style>
