<script>
    export let value = ''
</script>

<div class="search-input">
    <div class="search-input__icon"></div>
    <input type="search" class="search-input__input" placeholder="search solution..." bind:value >
</div>


<style lang="scss">
    .search-input {
        display: flex;
        align-items: center;

        &__icon {
            background: url('/search-icon.png');
            width: 16px;
            height: 24px;
            opacity: 0.6;
        }
        &__input {
            position: relative;
            background: transparent;
            width: 100%;
            color: #0c0b0b;
            padding-bottom: 10px;
            border: none;
                border-bottom: solid 1px rgba(146, 87, 76, 0.24);
            border-radius: 0;
            mask-border-width: 300px;
            outline: none;
            transition: border ease 0.25s;

            &:focus {
                border-bottom-color: #99626f;
            }

            &::placeholder {
                color: #9b5858;
            }

            &::-webkit-search-cancel-button {
                /* Remove default */
                appearance: none;

                background: url('/cancel-icon.png');
                width: 12px;
                height: 12px;
                opacity: 0.75;
                cursor: pointer;
                transition: opacity ease 0.25s;

                &:hover {
                    opacity: 1;
                }
            }
        }
    }
</style>