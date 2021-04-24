<script>
import { createEventDispatcher } from 'svelte';

    import { fade } from 'svelte/transition';

    const emit = createEventDispatcher()

    export let readable = 'readable'
    export let id = 'id'
</script>

<button class="search-result" transition:fade={{ duration: 450 }} on:click={() => emit('selected')}>
    <div class="search-result__readable">{@html readable}</div>
    <div class="search-result__id">{@html id}</div>
</button>

<style lang="scss">
    @import '../../sass/main';
    
    .search-result {
        display: flex;
        justify-content: space-between;
        background: transparent;
        width: 100%;
        padding: 10px 8px;
        margin: 0;
        color: #1a1616;
        border: none;
        outline: none;
        box-sizing: border-box;
        cursor: pointer;
        transition: background ease 0.25s;

        &:hover {
            @include glassyPanelSingle(rgba(201, 199, 199, 0.576));
        }
        &:focus {
            outline: solid 1px #ff9da1;
        }
        &:focus-visible {
            @include glassyPanelSingle(#a7a7a7);
        }

        &__id {
            font-size: 0.9em;
            opacity: 0.6;
        }
    }
</style>