<script>
    import { createEventDispatcher } from "svelte";

    const emit = createEventDispatcher()
    export let readable='button'

    export let isActive = false

    const handleClick = () => {
        isActive = !isActive
        emit('selected')
    }
</script>

<button class="toggle-button {isActive ? 'active' : ''}" on:click={handleClick}>
    {@html readable}
</button>

<style lang="scss">
    .toggle-button {
        &:hover {
            cursor: pointer;
        }
        &.active {
            background: green;
        }
    }
</style>