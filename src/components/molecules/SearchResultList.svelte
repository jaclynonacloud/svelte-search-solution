<script>
    import SearchResult from "../atoms/SearchResult.svelte";

    export let results = [
        { id: 'carrot', readable: 'Carrot' },
        { id: 'zucchini', readable: 'Zucchini'}
    ]
</script>

<div class="search-result-list">
    {#each results as {readable, id}}
    <SearchResult {readable} {id} />
    {/each}
</div>