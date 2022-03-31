<script>
    import { onMount } from "svelte";
    import Button from "../common/Button.svelte";
    import BookGrid from "../library/BookGrid.svelte";
    import { httpGet } from "../common/api.js";

    let books = [];
    onMount(async function () {
        const { data } = await httpGet("/?_sort=id&_order=desc");
        books = data;
    });
</script>

<div>
    <header>
        <span class="preamble">Welcome to the</span>
        <h1>Library</h1>
    </header>

    <p class="greeting">
        This is a library for the people. Welcome. Read the books here. Be
        inspired. Go home, and share them with your family.
    </p>

    <Button to="/create">+ Add book</Button>
    <BookGrid {books} />
</div>

<style></style>
