<script>
	import Notification from './components/atoms/Notification.svelte'
	import SearchSolution from './components/organisms/SearchSolution.svelte'

	const data = {
		fruits: [
			{ id: 'banana', readable: 'Banana' },
			{ id: 'apple', readable: 'Apple'},
			{ id: 'pear', readable: 'Pear' },
			{ id: 'watermelon', readable: 'Watermelon' },
			{ id: 'grapefruit', readable: 'Grapefruit' },
			{ id: 'grapes', readable: 'Grapes' },
			{ id: 'lemon', readable: 'Lemon' }
		],
		berries: [
			{ id: 'blueberry', readable: 'Blueberry'},
			{ id: 'strawberry', readable: 'Strawberry' },
			{ id: 'blackberry', readable: 'Blackberry' },
			{ id: 'raspberry', readable: 'Raspberry' }
		],
		vegetables: [
			{ id: 'carrot', readable: 'Carrot' },
			{ id: 'zucchini', readable: 'Zucchini'}
		]
	}

	let value = ''
</script>

<main>
	<SearchSolution {data} key="fruits" bind:value />
	<Notification readable={value} />
</main>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Quicksand&display=swap');

	:global(html),
	:global(body) {
		background: radial-gradient(#382e63, #140a08), radial-gradient(closest-side at 25% 60%, #af7b0b, #c23a19);
		background-blend-mode: lighten;
	}

	main {
		display: flex;
		justify-content: center;
		align-items: center;
		width: 100%;
		height: 100%;
		font-family: 'Quicksand', sans-serif;
	}

	
</style>