<script>
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


<footer id="foot" class="bg-[#104351] py-20">
    <div class="row justify-center py-5">
    <div class="grid grid-cols-4">
        <div class="links text-center">
            <dl>
                <dt><b>SHOP</b></dt>
                {#each shop as link}
                <dd><a class="hover:text-[#f0a424] font-serif" href="https://www.brightendeavors.com/{link.link}/">{link.name}</a></dd>
                {/each}
            </dl>
        </div>
        <div class="links text-center">
            <dl>
                <dt><b>PARTNERS</b></dt>
                {#each partners as link}
                <dd><a class="hover:text-[#f0a424] font-serif" href="https://www.brightendeavors.com/{link.link}/">{link.name}</a></dd>
                {/each}
            </dl>
        </div>
        <div class="links text-center">
            <dl>
                <dt><b>MISSION</b></dt>
                {#each mission as link}
                <dd><a class="hover:text-[#f0a424] font-serif" href="https://www.brightendeavors.com/{link.link}/">{link.name}</a></dd>
                {/each}
            </dl>
        </div>
        <div class="links text-center">
            <dl>
                <dt><b>FAQs</b></dt>
                {#each faq as link}
                <dd><a class="hover:text-[#f0a424] font-serif" href="https://www.brightendeavors.com/{link.link}/">{link.name}</a></dd>
                {/each}
            </dl>
        </div>
    </div>
    </div>
</footer>

<section id="subfoot">
    <div class="flex w-full flex-col items-center justify-center bg-[#F0A424] text-[#104351] py-4 px-4">
    <div>
        Copyright © 2023 Bright Endeavors
    </div>
    </div>
</section>
