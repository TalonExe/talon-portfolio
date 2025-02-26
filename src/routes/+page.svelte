<script>
    import Navbar from "$lib/components/Navbar/Navbar.svelte"
	import { onMount } from "svelte";

    let hackertitle = "HackerMan";
    let charset = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
    let titlechar = $state();
    let interval = null
    let isAnimating = false;

    let onHackEffect = () => {

        if (isAnimating) return;

        isAnimating = true;

        if (interval) clearInterval(interval);
        let iteration = 0
        interval = setInterval(() => {

            titlechar = hackertitle.split('')

            titlechar = titlechar.map((char,index) => {
                if (index < iteration) return hackertitle[index];
                return charset[Math.floor(Math.random() * charset.length)]
            })

            titlechar = titlechar.join("")

            if (iteration >= hackertitle.length){
                clearInterval(interval)
                interval = null
                isAnimating = false
            }
            
            iteration += 1 / 5
        }, 30)
    }

    onMount(() => {
        onHackEffect()
    })
</script>

<!-- TODO -->
<!-- make navbar -->
<div class="flex w-screen justify-between px-42 py-10 sticky top-0 left-0 bg-black-primary">
    <div class="text-3xl">
        HL
    </div>
    <Navbar />
</div>

<!-- MAKE HERO section -->
<main class="h-screen bg-green-primary">
    <div class="h-full w-full flex justify-center items-center">
        <!-- svelte-ignore a11y_mouse_events_have_key_events -->
        <h1 class="text-black text-4xl font-bold uppercase font-hacked hacked" onmouseover={onHackEffect}>
            {titlechar || hackertitle}
        </h1>
    </div>
</main>

<!-- make project section -->
<div>
    this is the project section
</div>
<!-- make about section -->
<div>
    this is the about section
</div>
<!-- make footer -->
<footer>
    this is the footer
</footer>