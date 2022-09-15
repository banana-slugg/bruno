<script lang="ts">
    import Profile from "./lib/Profile.svelte";
    import SideConf from "./lib/SideConf.svelte";
    import ScreenConf from "./lib/ScreenConf.svelte";
    import Title from "./lib/Title.svelte";
</script>

<main>
    <ScreenConf />
    <!-- -->

    <div class="h-screen z-10">
        <div class="grid grid-flow-col auto-cols-auto h-full justify-items-center place-items-center">
            <SideConf />
            <div class="grid grid-flow-row auto-rows-auto justify-items-center text-center place-items-center h-full">
                <Title />
                <Profile />
            </div>
            <SideConf />
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
