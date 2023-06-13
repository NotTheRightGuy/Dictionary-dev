<script>
	import '../icons/css/all.css';

	import Header from '../components/Header.svelte';
	import Input from '../components/Input.svelte';
	import Word from '../components/Word.svelte';
	import Meaning from '../components/Meaning.svelte';
	import Source from '../components/Source.svelte';

	let word = 'keyboard';
	let pronunciation = '';

	let meaning = [
		{
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
			]
		},
		{
			partOfSpeech: 'verb',
			definitions: [
				{
					definition: 'to enter (information) into a computer by using a keyboard'
				},
				{
					definition: 'to play (a musical instrument) by using a keyboard'
				}
			]
		}
	];

	let link = 'https://www.merriam-webster.com/dictionary/keyboard';

	function fetchDict(word) {
		fetch(`https://api.dictionaryapi.dev/api/v2/entries/en/${word}`)
			.then((response) => response.json())
			.then(async (data) => {
				console.log(data);
				pronunciation = data[0].phonetics[2].text;
				meaning = await data[0].meanings;
				link = await data[0].sourceUrls[0];
			});
	}
</script>

<div class="outer-container">
	<div class="inner-container">
		<Header />
		<Input
			on:search={(search) => {
				word = search.detail;
				fetchDict(word);
			}}
		/>
		<Word {word} {pronunciation} />
		{#each meaning as mean}
			<Meaning meaning={mean} />
		{/each}
		<Source {link} />
	</div>
</div>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500&display=swap');
	@import url('https://fonts.googleapis.com/css2?family=Lato&display=swap');
	@import url('https://fonts.googleapis.com/css2?family=Inconsolata&display=swap');

	:root {
		--font-serif: 'Playfair Display', serif;
		--font-sans-serif: 'Lato', sans-serif;
		--font-mono: 'Inconsolato', monospace;
		--bg-light: white;
		--color-white: hsla(0, 0%, 100%, 1);
		--color-purple: hsla(274, 82%, 60%, 1);
		--color-purple-25: hsla(274, 82%, 60%, 0.25);
		--color-border-right: hsla(0, 0%, 91%, 1);
		--color-gray: hsla(0, 0%, 46%, 1);
		--color-red: hsla(0, 100%, 66%, 1);
	}

	.outer-container {
		display: flex;
		justify-content: center;
		height: 100vh;
	}

	.inner-container {
		width: 100%;
		max-width: 700px;
	}
</style>
