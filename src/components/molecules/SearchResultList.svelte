<script>
    import SearchResult from "../atoms/SearchResult.svelte";

    export let results = []
</script>

<div class="search-result-list">
    {#each results as {readable, id}}
    <SearchResult {readable} {id} />
    {/each}
</div>