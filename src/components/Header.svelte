<script>
	let toggled = false;
	let elem;
	let icon;
	function handleToggle() {
		if (!toggled) {
			elem.style.transform = 'translateX(1.3rem)';
		} else {
			elem.style.transform = 'translateX(0rem)';
		}
		toggled = !toggled;
	}
</script>

<header>
	<div class="fa-solid fa-book fa-2x" />
	<div class="options">
		<select name="font" id="font">
			<option value="">Serif</option>
			<option value="">Sans-Serif</option>
			<option value="">Mono</option>
		</select>
		<!-- svelte-ignore a11y-click-events-have-key-events -->
		<div class="toggle-switch" on:click={handleToggle}>
			<div class="ball" bind:this={elem} />
		</div>
		<div class={!toggled ? 'fa-regular fa-moon moon' : 'fa-regular fa-sun sun'} bind:this={icon} />
	</div>
</header>

<style>
	.toggle-switch {
		width: 2.3rem;
		height: 1rem;
		background-color: var(--color-gray);
		border-radius: 1rem;
		display: flex;
		align-items: center;
		padding: 0.2rem;
		cursor: pointer;
	}

	.ball {
		width: 0.9rem;
		height: 0.9rem;
		background-color: var(--color-white);
		border-radius: 50%;
		transition: transform 0.2s ease-in-out;
	}
	header {
		margin-top: 3rem;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.options {
		display: flex;
		gap: 2rem;
	}
	select {
		border: 0;
		font-family: var(--font-serif);
		font-weight: bold;
		font-size: 1.1rem;
		outline: 0;
		margin-right: 0px;
	}
	.moon {
		font-size: 1.4rem;
		transform: rotate(-30deg);
	}
	.sun {
		font-size: 1.4rem;
	}
</style>
