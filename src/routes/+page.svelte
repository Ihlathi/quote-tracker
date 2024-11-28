<script lang="ts">
    import QuoteInput from "../components/QuoteInput.svelte";
    import QuoteList from "../components/QuoteList.svelte";

    let quotes: {quote: string; attribution: string}[] = [];

    const handleAddQuote = (quote: string, attribution: string): void => {
        quotes = [...quotes, {quote, attribution}];
    };
</script>

<h1>Quote Tracker</h1>
<QuoteInput onAddQuote={handleAddQuote}/>
<QuoteList {quotes}/>
