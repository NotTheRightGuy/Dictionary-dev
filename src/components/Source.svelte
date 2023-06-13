<script>
	export let link;
</script>

<section>
	<hr />
	<div>
		<span>Source</span>
		<a href={link}>{link}</a>
		<i class="fa-solid fa-arrow-up-right-from-square" />
	</div>
</section>

<style>
	section {
		height: 6rem;
	}
	span {
		text-decoration: underline;
		font-family: var(--font-serif);
		font-size: 0.9rem;
		font-weight: bold;
		opacity: 0.6;
	}
	a {
		margin-left: 30px;
		text-decoration: underline;
		font-family: var(--font-serif);
		font-size: 0.7rem;
	}
	i {
		opacity: 0.5;
	}
</style>
