<script>
    let yardımSiteleri = [
        {
            "name": "AKUT",
            "message": "AKUT yazıp 2930'a SMS gönderebilirsiniz. (10TL)",
            "url": "https://www.akut.org.tr/bagis-yap"
        },
        {
            "name": "AFAD",
            "message": "DEPREM yazıp 1866'a SMS gönderebilirsiniz. (20TL)",
            "url": "https://www.afad.gov.tr/depremkampanyasi2"
        },
        {
            "name": "KIZILAY",
            "message": "DEPREM yazıp 2868'e SMS gönderebilirsiniz. (15TL)",
            "url": "https://www.kizilay.org.tr/bagis"
        },
        {
            "name": "AHBAP",
            "message": "AHBAP üzerinden sizde deprem bölgesine yardım edebilirsiniz.",
            "url": "https://ahbap.org/"
        },
        {
            "name": "Otelz",
            "message": "Depremzedeler için ücretsiz konaklama imkanı.",
            "url": "https://www.otelz.com/tr/gecmisolsunturkiyem"
        },
        {
            "name": "Teyitli Tweetler",
            "message": "Doğru olan tweetleri görebilir ve bu sayede daha hızlı sonuç alabiliriz.",
            "url": "https://twitter.com/MDepremyard"
        }
    ]
</script>

{#each yardımSiteleri as siteler}
<div class="transition-all duration-200 relative inline-block mx-3 my-3 md:my-3 lg:my-3 w-80 h-44 left-4 md:left-[4.3rem] lg:left-[9.3rem] top-5 rounded bg-[#131314]">
    <div>
        <h2 class="transition-all duration-200 px-3 ml-2 text-white font-semibold relative mt-5 text-md md:text-md lg:text-md">{siteler.name}</h2>
        <p class="transition-all duration-200 px-3 ml-2 text-gray-500 font-normal relative mt-1 text-md md:text-md lg:text-md">{siteler.message}</p>
        <div class="float-right relative top-8">
            <a href="{siteler.url}" class="relative w-10 p-3 mx-5 rounded bg-[#0b0b0c]">Siteye Git</a>
        </div>
    </div>
</div>
{/each}