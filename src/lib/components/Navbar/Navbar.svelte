<script>
    import Navlink from "./Navlink.svelte";

    let titles = ["Home", "Projects", "About", "Contact"]
</script>

<ul class="flex justify-between w-xl">
    {#each titles as title}
    <li>
        <Navlink title={title} url="#"/>
    </li>
    {/each}
</ul>