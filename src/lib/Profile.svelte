<script>
    import { fly } from "svelte/transition";
    import Quote from "./Quote.svelte";
    import { onMount } from "svelte";

    import src from "../assets/bruno.png";

    let ready = false;
    onMount(() => (ready = true));
</script>

{#if ready}
    <div class="grid grid-flow-row auto-rows-max gap-12" in:fly={{ x: 200, duration: 2000, delay: 3000 }}>
        <h1 class="text-base xl:text-4xl">Brandon "Rayim" Windermuth</h1>

        <div class="w-full flex items-center justify-center">
            <img {src} alt="bruno" class="w-96 mx-0 xl:mx-96 shadow-2xl justify-center" />
        </div>
        <Quote />
    </div>
{/if}
