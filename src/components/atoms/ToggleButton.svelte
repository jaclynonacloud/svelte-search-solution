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
    @import '../../sass/main';
    
    .toggle-button {
        @include glassyPanelSingle(rgb(168, 168, 168));
        padding: 8px 16px;
        margin: 5px 8px;
        border: none;
        transition: background ease 0.25s;

        &:hover {
            background: mix(transparent, white, 65);
            cursor: pointer;
        }
        &:focus {
            outline: solid 1px white;
        }
        &.active {
            background: #e9dfdd;
        }
    }
</style>