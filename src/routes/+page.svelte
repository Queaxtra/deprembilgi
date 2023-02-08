<script>
    import DestekOl from "../lib/destekOl.svelte";
    import DepremData from "../lib/depremData.svelte";
    import Footer from "../components/Footer.svelte";
</script>

<div>
    <div>
        <h2 class="transition-all duration-200 ml-7 md:ml-[5rem] lg:ml-40 text-white font-semibold relative mt-20 md:mt-32 lg:mt-32 text-2xl md:text-4xl lg:text-4xl">Son Depremler</h2>
        <p class="transition-all duration-200 ml-7 md:ml-[5rem] lg:ml-40 text-gray-500 font-normal relative mt-2 text-md md:text-md lg:text-md"><i class="fa-solid fa-circle-exclamation"></i> En son gerçekleşen <b>10</b> depremi gösterir.</p>
        <DepremData />
    </div>
    
    <div>
        <h2 class="transition-all duration-200 ml-7 md:ml-[5rem] lg:ml-40 text-white font-semibold relative mt-20 md:mt-32 lg:mt-32 text-2xl md:text-4xl lg:text-4xl">Destek Ol</h2>
        <DestekOl />
    </div>

    <Footer />
</div>
