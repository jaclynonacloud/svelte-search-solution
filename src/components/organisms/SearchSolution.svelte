<script>
    import SearchInput from '../atoms/SearchInput.svelte'
    import ToggleButtonGroup from '../molecules/ToggleButtonGroup.svelte'
    import SearchResultList from '../molecules/SearchResultList.svelte'

    export let data = {}
    export let key = ''
    
    let search = ''

    $: options = Object.keys(data)
    $: results = data[key]
</script>

<section class="search-solution">
    <SearchInput bind:value={search} />
    <ToggleButtonGroup {options} bind:value={key} />
    <SearchResultList {results} filter={search} />
    <div class="search-solution__footer">esc to quit</div>
</section>

<style lang="scss">
    .search-solution {
        background: #4a4a75;
        padding: 10px;
        color: white;
        
        &__footer {
            background: #5a2d2d;
            padding: 5px;
        }
    }
</style>