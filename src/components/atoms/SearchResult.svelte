<script>
import { createEventDispatcher } from 'svelte';

    import { fade } from 'svelte/transition';

    const emit = createEventDispatcher()

    export let readable = 'readable'
    export let id = 'id'
</script>

<div class="search-result" transition:fade={{ duration: 450 }} on:click={() => emit('selected')}>
    <div class="search-result__readable">{@html readable}</div>
    <div class="search-result__id">{@html id}</div>
</div>

<style lang="scss">
    .search-result {
        display: flex;
        justify-content: space-between;
        padding: 10px 8px;
        color: #1a1616;
        box-sizing: border-box;
        cursor: pointer;
        transition: background ease 0.25s;

        &:hover {
            background: rgba(255, 255, 255, 0.336);
        }

        &__id {
            font-size: 0.9em;
            opacity: 0.6;
        }
    }
</style>