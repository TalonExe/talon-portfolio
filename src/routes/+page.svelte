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
<div class="flex w-screen justify-between px-42 py-10 fixed top-0 bg-black-primary">
    <div class="text-3xl">
        HL
    </div>
    <Navbar />
</div>

<!-- MAKE HERO section -->
<main class="h-[90vh] bg-green-primary">
    <div class="h-full w-full flex justify-center items-center">
        <!-- svelte-ignore a11y_mouse_events_have_key_events -->
        <h1 class="text-black text-4xl font-bold uppercase font-hacked hacked" onmouseover={onHackEffect}>
            {titlechar || hackertitle}
        </h1>
    </div>
</main>

<!-- make project section -->
<div class="flex flex-col h-screen w-full">
    <h1>
        My Projects!!!
    </h1>
    <div class="flex flex-row">
        <div class="card bg-base-100 w-96 shadow-sm">
            <figure>
              <img
                src="https://img.daisyui.com/images/stock/photo-1606107557195-0e29a4b5b4aa.webp"
                alt="Shoes" />
            </figure>
            <div class="card-body">
              <h2 class="card-title">Card Title</h2>
              <p>A card component has a figure, a body part, and inside body there are title and actions parts</p>
              <div class="card-actions justify-end">
                <button class="btn btn-primary">Buy Now</button>
              </div>
            </div>
          </div>
          <div class="card bg-base-100 w-96 shadow-sm">
            <figure>
              <img
                src="https://img.daisyui.com/images/stock/photo-1606107557195-0e29a4b5b4aa.webp"
                alt="Shoes" />
            </figure>
            <div class="card-body">
              <h2 class="card-title">Card Title</h2>
              <p>A card component has a figure, a body part, and inside body there are title and actions parts</p>
              <div class="card-actions justify-end">
                <button class="btn btn-primary">Buy Now</button>
              </div>
            </div>
          </div>
          <div class="card bg-base-100 w-96 shadow-sm">
            <figure>
              <img
                src="https://img.daisyui.com/images/stock/photo-1606107557195-0e29a4b5b4aa.webp"
                alt="Shoes" />
            </figure>
            <div class="card-body">
              <h2 class="card-title">Card Title</h2>
              <p>A card component has a figure, a body part, and inside body there are title and actions parts</p>
              <div class="card-actions justify-end">
                <button class="btn btn-primary">Buy Now</button>
              </div>
            </div>
          </div>
    </div>
</div>

<!-- make about section -->
<div>
    this is the about section
</div>
<!-- make footer -->
<footer>
    this is the footer
</footer>