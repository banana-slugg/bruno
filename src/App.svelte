<script lang="ts">
    import { fly, fade } from "svelte/transition";
    import { Confetti } from "svelte-confetti";
    import { onMount } from "svelte";
    import Quote from "./lib/Quote.svelte";

    import src from "./assets/bruno.png";

    let ready = false;
    onMount(() => (ready = true));
</script>

<main>
    <div class="fixed -top-8 left-0 h-screen w-screen flex justify-center overflow-hidden">
        <Confetti
            x={[-5, 5]}
            y={[0, 0.1]}
            delay={[1000, 2000]}
            infinite
            duration="5000"
            amount="500"
            fallDistance="100vh"
        />
    </div>
    <!-- -->
    <div class="flex flex-col items-center justify-center h-screen overflow-hidden">
        {#if ready}
            <h1 class="text-base xl:text-6xl mb-10" in:fade={{ duration: 2000 }}>
                🥇 The <em>Piece of the Year</em> Award goes to... 🥇
            </h1>
        {/if}

        <div class="flex justify-between items-end">
            <Confetti amount="200" noGravity x={[-1.5, 0.5]} y={[10, 15]} />
            <div class="items-center justify-center text-center flex">
                {#if ready}
                    <div
                        class="grid grid-flow-row auto-rows-max gap-12"
                        in:fly={{ x: 200, duration: 2000, delay: 4000 }}
                    >
                        <h1 class="text-base xl:text-4xl">Brandon "Rayim" Windermuth</h1>

                        <div class="w-full flex items-center justify-center">
                            <img {src} alt="bruno" class="w-96 mx-0 xl:mx-96 shadow-2xl justify-center" />
                        </div>
                        <Quote />
                    </div>
                {/if}
            </div>
            <Confetti amount="200" noGravity x={[-1.5, 0.5]} y={[10, 15]} />
        </div>
    </div>
</main>

<style global lang="postcss">
    @import url("https://fonts.googleapis.com/css2?family=Roboto&display=swap");
    @tailwind base;
    @tailwind components;
    @tailwind utilities;

    body {
        font-family: Roboto, "Helvetica Neue", Arial, sans-serif;
        @apply m-0 antialiased bg-zinc-900;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
    }

    h1 {
        @apply text-white font-medium tracking-wide;
    }
</style>
