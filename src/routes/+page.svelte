<script>
  import ThreeItemGrid from '$components/ThreeItemGrid.svelte';
  import Carousel from '$components/Carousel.svelte';

  /** @type {import('./$types').PageData} */
  export let data;

  $: clothesCollection = data.products[0]?.node?.products?.edges;
  $: featuredCollection = data.products[1]?.node?.products?.edges;
</script>

<svelte:head>
  <title>Home – SvelteKit Commerce</title>
</svelte:head>

<main>
  <section>
    <br><br><br><br><br>
    <h1 class="bg-white text-[#991F36] text-[40px] font-serif font-semibold text-center pt-10">~ Classic Collection ~</h1>

    <div class="lg:h-[75vh]">
      <ThreeItemGrid products={featuredCollection} />
    </div>

    <div class="lg:h-[90vh]">
      <ThreeItemGrid products={featuredCollection} />
    </div>
  </section>
</main>
