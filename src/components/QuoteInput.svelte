<script lang="ts">
	import { on } from "svelte/events";

    let quote: string = '';
    let attribution: string = '';

    export let onAddQuote: (quote: string, attribution: string) => void;

    const addQuote = () => {
        onAddQuote(quote, attribution);
        quote = '';
        attribution = '';
    };
</script>

<div>
    <!--quote box-->
    <input 
    type="text" 
    bind:value={quote} 
    placeholder="Enter Quote" 
    class="input p-2 border border-gray-300 rounded-md mb-2"
    />

   <!--attribution box-->
    <input
    type="text"
    bind:value={attribution}
    placeholder="Speaker"
    class="input p-2 border border-gray-300 rounded-md mb-2"
    />

    <!--add button-->
    <button
    on:click={addQuote}
    class="btn p-2 bg-blue-500 text-white rounded-md">
    Add Quote
    </button>
</div>