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
    @import '../../sass/main';

    .search-solution {
        display: flex;
        flex-flow: column;
        @include glassyPanel(#bba29c);
        width: 100%;
        max-width: 450px;
        padding: 10px;
        color: white;
        border: solid 1px #ff515a;
        box-shadow: 0 0 35px rgba(39, 21, 21, 0.5);
        
        &__footer {
            align-self: center;
            @include glassyPanelSingle(#b4b4b4);
            color: #9b5858;
            padding: 5px 8px;
            font-size: 0.75em;
            font-style: italic;
            text-align: center;
            border-radius: 2px;
            cursor: default;
        }

        :global(::-webkit-scrollbar) {
            background: #7c2d38;
            width: 5px;
            border-radius: 2px;
        }
        :global(::-webkit-scrollbar-thumb) {
            background: #ee4c54;
            border-radius: 2px;

            &:hover {
                background: #ff7974;
            }
        }
    }
</style>