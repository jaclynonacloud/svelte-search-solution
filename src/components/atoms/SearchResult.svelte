<script>
    export let readable = 'readable'
    export let id = 'id'
</script>

<div class="search-result">
    <div class="search-result__readable">{@html readable}</div>
    <div class="search-result__id">{@html id}</div>
</div>

<style lang="scss">
    .search-result {
        display: flex;
        justify-content: space-between;

        &__id {
            font-size: 0.9em;
            opacity: 0.6;
        }
    }
</style>