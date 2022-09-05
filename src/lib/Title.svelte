<script>
    import { fade } from "svelte/transition";
    import { onMount } from "svelte";

    let ready = false;
    onMount(() => (ready = true));
</script>

{#if ready}
    <h1 class="text-base xl:text-6xl" in:fade={{ duration: 2000 }}>
        🥇 The <em>Piece of the Year</em> Award goes to... 🥇
    </h1>
{/if}
