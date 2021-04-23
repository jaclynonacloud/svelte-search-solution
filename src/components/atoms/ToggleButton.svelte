<script>
    import { createEventDispatcher } from "svelte"

    const emit = createEventDispatcher()

    export let readable='button'
    export let isActive = false

    const handleClick = () => {
        isActive = !isActive
        emit('toggled', isActive)
    }
</script>

<button class="toggle-button {isActive ? 'active' : ''}" on:click={handleClick}>
    {@html readable}
</button>

<style lang="scss">
    .toggle-button {
        background: mix(transparent, white, 85);
        padding: 8px 16px;
        margin: 5px 8px;
        border: none;
        outline: none;
        transition: background ease 0.25s;

        &:hover {
            background: mix(transparent, white, 65);
            cursor: pointer;
        }
        &.active {
            background: #e9dfdd;
        }
    }
</style>