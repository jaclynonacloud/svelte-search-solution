<script>
    import { createEventDispatcher } from "svelte";
    import ToggleButton from "../atoms/ToggleButton.svelte"

    const emit = createEventDispatcher()

    export let value = ''
    export let options = ['hello', 'world']

    const handleSelected = option => {
        value = option
        emit('input', value)
    }
</script>

<div class="toggle-button-group">
    {#each options as option}
    <ToggleButton readable={option} on:selected={() => handleSelected(option)} isActive={value === option} />
    {/each}
</div>