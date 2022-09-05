<script>
    import { Confetti } from "svelte-confetti";
</script>

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
