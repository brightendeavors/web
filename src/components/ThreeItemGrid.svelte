<script>
  import GridTile from '$components/GridTile.svelte';
  //price={products[0].node.priceRange.maxVariantPrice.amount}
  export let products;
</script>

<div class="flex flex-col lg:h-full lg:flex-row bg-white w-full">
  <div class="w-full lg:h-full lg:w-1/3 ml-[10vh] mt-[10vh]">
    <GridTile
      href={`/product/${products[0].node.handle}`}
      title={products[0].node.title}
      min_price=8.00
      max_price=22.00
      theme="Floral"
      imageSrc={products[0].node.images.edges[0].node.originalSrc}
    />
  </div>
  <div class="w-full lg:h-full lg:w-1/3 ml-[1vh] mt-[10vh]">
    <GridTile
    href={`/product/${products[1].node.handle}`}
    title={products[1].node.title}
    min_price=8.00
    max_price=22.00
    theme="Floral"
    imageSrc={products[1].node.images.edges[0].node.originalSrc}
    />
  </div>
  <div class="w-full lg:h-full lg:w-1/3 mr-[11vh] ml-[2vh] mt-[10vh] ">
    <GridTile
    href={`/product/${products[2].node.handle}`}
    title={products[2].node.title}
    min_price=8.00
    max_price=22.00
    theme="Floral"
    imageSrc={products[2].node.images.edges[0].node.originalSrc}
    />
  </div>
</div>
