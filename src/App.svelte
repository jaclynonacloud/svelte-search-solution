<script>
	import SearchSolution from './components/organisms/SearchSolution.svelte'

	const data = {
		fruits: [
			{ id: 'banana', readable: 'Banana' },
			{ id: 'apple', readable: 'Apple'},
			{ id: 'pear', readable: 'Pear' },
			{ id: 'watermelon', readable: 'Watermelon' }
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
</script>

<main>
	<SearchSolution {data} />
</main>

<style>
	:global(html),
	:global(body) {
		display: flex;
		justify-content: center;
		align-items: center;
		background: grey;
	}
</style>