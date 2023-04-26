<script>
    import LogoFooter from "./LogoFooter.svelte";

    let shop = [{name:"Shop All", link:"shop"}, {name:"Candles",
                link:"candle-collections"}, {name:"Diffusers", link:"diffusers"},
                {name:"Gift Sets", link:"gift-sets"}];

    let partners = [{name:"Wholesale", link:"wholesale"}, {name:"Corporate Gifting", link:"corporategifting"},
                    {name:"Stockists", link:"stockists"}];

    let mission = [{name:"Our Story", link:"our-story"}, {name:"Blog", link:"blog"},
                   {name:"Media", link:"media"}, {name:"New Moms", link:"https://newmoms.org/"},
                   {name:"Apply for Job Training", link:"https://newmoms.org/job-training-intake-form"}];

    let faq = [{name:"Contact", link:"contact"}, {name:"FAQs", link:"faqs"},
                {name:"Shipping & Returns", link:"shipping-info"}, {name:"Local Pick-Up", link:"local-pick-up"},
                {name:"Sitemap", link:"sitemap_index.xml"}];
</script>


<footer id="foot" class="bg-[#104351] pt-2">
    <div class="row justify-center">
    <div class="grid grid-cols-6 items-center">
        <div class="col-span-2">
            <LogoFooter/>
        </div>

        <div class="links text-center pb-20">
            <dl>
                <dt class="pb-2 tracking-[.20em] text-sm"><b>SHOP</b></dt>
                {#each shop as link}
                <dd class="mb-px"><a class="hover:text-[#f0a424] font-serif text-xs" href="https://www.brightendeavors.com/{link.link}/">{link.name}</a></dd>
                {/each}
            </dl>
        </div>
        <div class="links text-center pb-28">
            <dl>
                <dt class="pb-2 tracking-[.20em] text-sm"><b>PARTNERS</b></dt>
                {#each partners as link}
                <dd class="mb-px"><a class="hover:text-[#f0a424] font-serif text-xs" href="https://www.brightendeavors.com/{link.link}/">{link.name}</a></dd>
                {/each}
            </dl>
        </div>
        <div class="links text-center pb-16">
            <dl>
                <dt class="pb-2 tracking-[.20em] text-sm"><b>MISSION</b></dt>
                {#each mission as link}
                <dd class="mb-px"><a class="hover:text-[#f0a424] font-serif text-xs" href="https://www.brightendeavors.com/{link.link}/">{link.name}</a></dd>
                {/each}
            </dl>
        </div>
        <div class="links text-center pb-16">
            <dl>
                <dt class="pb-2 tracking-[.20em] text-sm"><b>FAQS</b></dt>
                {#each faq as link}
                <dd class="mb-px"><a class="hover:text-[#f0a424] font-serif text-xs" href="https://www.brightendeavors.com/{link.link}/">{link.name}</a></dd>
                {/each}
            </dl>
        </div>
    </div>
    </div>
</footer>

<section id="subfoot">
    <div class="flex w-full flex-col items-center justify-center bg-[#F0A424] text-[#104351] py-3 px-4">
    <div>
        Copyright © 2023 Bright Endeavors
    </div>
    </div>
</section> 
