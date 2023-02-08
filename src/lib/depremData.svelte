<script lang="ts">
    import { onMount } from "svelte";
    let url = import.meta.env.VITE_APP_DEPREM_API;
    let depremData: any[] = [];
    onMount(async () => {
        fetch(url).then(res => res.json()).then(json => {
            depremData = json.result;
            depremData = depremData.slice(0, 10);

            console.log(depremData);
        });
    });
</script>

{#each depremData as deprem}
<div class="transition-all duration-200 relative inline-block mx-3 my-3 md:my-3 lg:my-3 w-80 h-40 left-4 md:left-[4.3rem] lg:left-[9.3rem] top-5 rounded bg-[#131314]">
    <div>
        <span class="relative ml-5 top-2 text-white/60"><i class="fa-regular fa-clock"></i> {deprem.date}</span>
        <h2 class="absolute ml-3 mt-2 p-2">{deprem.lokasyon}</h2>
        {#if deprem.mag >= 1.0 && deprem.mag <= 3.9}
        <h2 class="transition-all duration-200 relative float-right mx-5 top-2 text-green-500/60">{deprem.mag}</h2>
        {:else if deprem.mag >= 4.0 && deprem.mag <= 4.9}
        <h2 class="transition-all duration-200 relative float-right mx-5 top-2 text-yellow-400/60">{deprem.mag}</h2>
        {:else if deprem.mag >= 5.0 && deprem.mag <= 5.9}
        <h2 class="transition-all duration-200 relative float-right mx-5 top-2 text-orange-500/60">{deprem.mag}</h2>
        {:else if deprem.mag >= 6.0 && deprem.mag <= 6.9}
        <h2 class="transition-all duration-200 relative float-right mx-5 top-2 text-red-500/60">{deprem.mag}</h2>
        {:else if deprem.mag >= 7.0}
        <h2 class="transition-all duration-200 relative float-right mx-5 top-2 text-red-500/60">{deprem.mag}</h2>
        {/if}

        <div class="float-right relative top-24">
            <a href="https://www.google.com/maps/place/{deprem.lokasyon}" class="relative w-10 p-3 mx-5 rounded bg-[#0b0b0c]">Görüntüle</a>
        </div>
    </div>
</div>
{:else}
<div class="text-center">
    <h2 class="text-white relative top-10 text-white/70"><i class="fa-solid fa-arrows-rotate animate-spin"></i> Yükleniyor..</h2>
</div>
{/each}