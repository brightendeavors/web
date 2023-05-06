<script>
  export let title = '';
  export let imageSrc;
  export let min_price = '';
  export let max_price = '';
  export let theme = '';
  export let href = '';

  //src={imageSrc};
</script>

<div class="container align-middle">
    <div class="text-black absolute z-10 w-[50vh] h-[50vh]">
        <a href="www.google.com">   
            <picture class="hover:opacity-5">
                <source type="image/jpeg" />
                <img
                alt="Bright Endeavors Logo"
                class="w-[50vh]"
                decoding="async"
                height={1024}
                loading="eager"
                src="./Fresh-Bouquet.jpeg"
                width={1024}
                />
            </picture>
        </a> 
        <div>
            <a href={href}><h6 class="font-serif text-[#224b59] uppercase tracking-[.25em] text-sm pt-5">{theme}</h6></a>
            <h2 class="font-serif text-[#991F36] text-lg font-bold tracking-widest pb-5">{title}</h2>
            <p class="font-serif text-[#224b59] font-bold">${min_price} - ${max_price}</p>
        </div>
    </div>

    <div class="relative hover:z-20 bg-[#224b59] flex flex-col mr-20 py-4 w-[50vh] h-[50vh]">
        <h1 class="text-white font-serif text-center text-lg text-[25px] hover:pb-32 pb-32 pt-32">View Product</h1>
        <div class="relative hover:z-40"><button class=" hover:text-white text-[#f0a424] font-serif border-2 border-solid border-[#f0a424] text-[20px] w-fit ml-[70px] px-4 py-2">SELECT AN OPTION</button></div>
    </div>
</div>



