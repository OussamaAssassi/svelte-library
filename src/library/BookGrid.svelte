<script>
    import BookCover from "../common/BookCover.svelte";
    import Heart from "../library/Heart.svelte";
    export let books = [];
</script>

<ul>
    {#each books as book}
        <li>
            <BookCover interactive {book} />
            {#if book.favorite}
                <div class="heart">
                    <Heart />
                </div>
            {/if}
        </li>
    {/each}
</ul>

<style>
    ul {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(10rem, 1fr));
        grid-template-columns: repeat(auto-fill, minmax(8rem, 1fr));
        grid-auto-rows: 12.8rem;
        gap: var(--spacingMedium);
        list-style: none;
        max-width: 100%;
        padding: 0;
    }
    li {
        position: relative;
        display: flex;
    }
    .heart {
        position: absolute;
        bottom: calc(-1 * var(--spacingSmall));
        right: calc(-1 * var(--spacingSmall));
    }
</style>
