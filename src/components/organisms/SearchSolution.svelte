<script>
    import SearchInput from '../atoms/SearchInput.svelte'
    import ToggleButtonGroup from '../molecules/ToggleButtonGroup.svelte'
    import SearchResultList from '../molecules/SearchResultList.svelte'

    export let data = {}
    export let key = ''
    export let value = ''
    
    let search = ''

    $: options = Object.keys(data)
    $: results = data[key] || []
</script>

<section class="search-solution">
    <SearchInput bind:value={search} />
    <ToggleButtonGroup {options} bind:value={key} />
    <SearchResultList {results} filter={search} bind:value />
    <div class="search-solution__footer">esc to quit</div>
</section>

<style lang="scss">
    .search-solution {
        display: flex;
        flex-flow: column;
        background: #bba29c;
        width: 100%;
        max-width: 450px;
        padding: 10px;
        color: white;
        border: solid 1px #dad2d0;
        box-shadow: 0 0 35px rgba(39, 21, 21, 0.5);
        
        &__footer {
            align-self: center;
            background: rgba(255, 255, 255, 0.2);
            color: #9b5858;
            padding: 5px 8px;
            font-size: 0.75em;
            font-style: italic;
            text-align: center;
            border-radius: 2px;
            cursor: default;
        }

        :global(::-webkit-scrollbar) {
            background: #8b7874;
            width: 5px;
            border-radius: 2px;
        }
        :global(::-webkit-scrollbar-thumb) {
            background: #e9dfdd;
            border-radius: 2px;

            &:hover {
                background: white;
            }
        }
    }
</style>