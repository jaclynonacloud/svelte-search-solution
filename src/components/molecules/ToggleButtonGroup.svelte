<script>
    import { createEventDispatcher } from "svelte"
    import ToggleButton from "../atoms/ToggleButton.svelte"

    const emit = createEventDispatcher()

    export let value = ''
    export let options = []

    const handleToggled = (option, toggle) => {
        console.log('toggle', toggle)
        value = toggle ? option : ''
        emit('input', value)
    }
</script>

<div class="toggle-button-group">
    {#each options as option}
    <ToggleButton readable={option} on:toggled={({detail}) => handleToggled(option, detail)} isActive={value === option} />
    {/each}
</div>