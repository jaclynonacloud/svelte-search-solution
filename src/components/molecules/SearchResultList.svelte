<script>
    import SearchResult from "../atoms/SearchResult.svelte"

    export let results = []
    export let filter = ''
    export let value = ''

    $: filteredResults = filter === '' ? results :
        results.filter(({readable, id}) => {
            if (readable.toLowerCase().indexOf(filter.toLowerCase()) !== -1) return true
            if (id.toLowerCase().indexOf(filter.toLowerCase()) !== -1) return true
            return false
        })
</script>

<div class="search-result-list">
    {#each filteredResults as {readable, id}}
    <SearchResult {readable} {id} on:selected={() => value = id} />
    {/each}
</div>

<style lang="scss">
    .search-result-list {
        padding: 4px;
        height: 200px;
        overflow-y: scroll;
    }
</style>