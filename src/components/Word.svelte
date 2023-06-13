<script>
	export let word;
	export let pronunciation;
</script>

<section>
	<div>
		<div id="word">{word}</div>
		{#if pronunciation}
			<div id="phone">{pronunciation}</div>
		{:else}
			<div id="phone">No pronunciation Found</div>
		{/if}
	</div>
	<div><button class="fa-solid fa-play" /></div>
</section>

<style>
	section {
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-top: 3rem;
	}
	#word {
		font-family: var(--font-serif);
		font-weight: bolder;
		font-size: 4rem;
	}
	#phone {
		color: var(--color-purple);
		font-size: 1.5rem;
		font-family: var(--font-serif);
		font-weight: bolder;
	}

	button {
		background-color: transparent;
		color: var(--color-purple);
		border: 0;
		font-size: 5rem;
	}

	.fa-play {
		transition: transform 0.2s ease-in-out;
	}
	.fa-play:hover {
		cursor: pointer;
		transform: scale(1.1);
	}
</style>
