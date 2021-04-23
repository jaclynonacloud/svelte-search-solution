<script>
    import SearchResult from "../atoms/SearchResult.svelte";

    export let results = []
    export let filter = ''

    $: filteredResults = filter === '' ? results :
        results.filter(({readable, id}) => {
            if (readable.toLowerCase().indexOf(filter.toLowerCase()) !== -1) return true
            if (id.toLowerCase().indexOf(filter.toLowerCase()) !== -1) return true
            return false
        })
</script>

<div class="search-result-list">
    {#each filteredResults as {readable, id}}
    <SearchResult {readable} {id} />
    {/each}
</div>