<script>
	export let meaning = {
		partOfSpeech: 'noun',
		definitions: [
			{ definition: 'a board with keys or buttons' },
			{
				definition:
					'a musical instrument that is played by means of a keyboard like that of a piano and that produces sounds electronically'
			},
			{
				definition:
					'a set of keys or buttons that are pushed to play a musical instrument (such as a piano) or computer or typewriter'
			}
		],
		synonyms: ['electronic keyboard', 'piano keyboard', 'qwerty keyboard'],
		antonyms: ['qwerty keyboard', 'piano keyboard', 'electronic keyboard'],
		example: 'This is an example'
	};
</script>

<section>
	<div class="divider-container">
		<div class="article">{meaning.partOfSpeech}</div>
		<div class="line-divide" />
	</div>

	<div id="meaning">Meaning</div>
	<div>
		{#each meaning.definitions as def}
			<div class="define">
				<div class="dot">.</div>
				<div class="definition">{def.definition}</div>
			</div>
			{#if def.example}
				<div class="exam">
					<div class="space" />
					<div class="example">"{def.example}"</div>
				</div>
			{/if}
		{/each}
	</div>
	<div class="syn">
		{#if meaning.synonyms && meaning.synonyms.length > 0}
			<div id="synonyms">Synonyms</div>
			<div class="syn-vals">
				{#each meaning.synonyms as syn}
					<div>{syn}</div>
				{/each}
			</div>
		{/if}
	</div>
	<div class="ant">
		{#if meaning.antonyms && meaning.antonyms.length > 0}
			<div id="antonyms">Antonyms</div>
			<div class="ant-vals">
				{#each meaning.antonyms as ant}
					<div>{ant}</div>
				{/each}
			</div>
		{/if}
	</div>
</section>

<style>
	.space {
		width: 1rem;
	}
	.exam {
		display: flex;
	}
	.dot {
		font-size: 2rem;
		font-weight: bold;
		color: var(--color-purple);
	}
	.define {
		display: flex;
		align-items: end;
		gap: 10px;
	}
	.example {
		font-family: var(--font-serif);
		font-weight: bold;
		opacity: 0.7;
		margin-top: 1rem;
		margin-bottom: 1rem;
		font-size: 1rem;
	}
	#synonyms {
		font-family: var(--font-serif);
		font-size: 1.2rem;
		font-weight: bold;
		margin-top: 3rem;
		opacity: 0.7;
	}
	#antonyms {
		font-family: var(--font-serif);
		font-size: 1.2rem;
		font-weight: bold;
		margin-top: 3rem;
		opacity: 0.7;
	}

	.definition {
		font-family: var(--font-serif);
		font-weight: bold;
		word-spacing: 4px;
		font-size: 1.1rem;
	}

	#meaning {
		font-family: var(--font-serif);
		font-size: 1.2rem;
		font-weight: bold;
		margin-top: 3rem;
		margin-bottom: 2rem;
		opacity: 0.5;
	}
	section {
		margin-top: 2rem;
		margin-bottom: 2rem;
	}
	.article {
		font-style: italic;
		font-family: var(--font-serif);
		font-weight: bold;
		font-size: 1.4rem;
		opacity: 0.9;
	}
	.divider-container {
		display: flex;
		align-items: center;
	}
	.line-divide {
		margin-left: 15px;
		width: 100%;
		height: 1px;
		opacity: 0.1;
		background-color: black;
	}
	.syn,
	.ant {
		display: flex;
		gap: 10px;
		align-items: end;
	}
	.syn-vals,
	.ant-vals {
		display: flex;
		flex-wrap: wrap;
		font-family: var(--font-serif);
		font-weight: bold;
		font-size: 1.1rem;
		color: var(--color-purple);
		gap: 10px;
	}
</style>
