<script>
    export let readable = ''
</script>

<div class="notification">
    {#if readable === ''}
    <div class="notification__empty">Select Item to Update</div>
    {:else}
    {@html readable}
    {/if}
</div>

<style lang="scss">
    .notification {
        position: fixed;
        bottom: 15px;
        left: 50%;
        background: #5f5f5f;
        padding: 12px 16px;
        color: white;
        border-radius: 6px;
        font-size: 1.3em;
        transform: translateX(-50%);

        &__empty {
            font-size: 0.8em;
            opacity: 0.7;
        }
    }
</style>