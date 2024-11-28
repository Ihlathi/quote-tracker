<script lang="ts">
    export let quotes: {quote: string; attribution: string}[] = [];

    const deleteQuote = (index: number): void => {
        quotes.splice(index, 1);
    };
</script>

<ul>
    {#each quotes as {quote, attribution}, index}
        <li>
            <blockquote>{quote}</blockquote>
            <footer>- {attribution}</footer>
            <button on:click={() => deleteQuote(index)}>Delete</button>
        </li>
    {/each}
</ul>