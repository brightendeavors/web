<script>
  import { page } from '$app/stores';
  import Icons from '$components/Icons.svelte';
  import { cartQuantity } from '../store';
  import SearchBar from '$components/SearchBar.svelte';
  import { createEventDispatcher } from 'svelte';

  import { slide } from 'svelte/transition'

  const dispatch = createEventDispatcher();

  $: currentRoute = $page.url.pathname;

  let showMenu = false;

  let tabs = [
    { name: 'shop', path: '/search' },
    { name: 'mission', path: '/search/featured' },
    { name: 'donate', path: '/search/clothes' },
    { name: 'wholesale', path: '/search/wholesale'}
  ];

  let sublinks = [
    { name: 'SHOP ALL', path: '/search' },
    { name: 'CANDLES', path: '/search/featured' },
    { name: 'DIFFUSERS', path: '/search/clothes' },
    { name: 'GIFT SETS', path: '/search/wholesale'},
    { name: 'MATCHES & ACCESSORIES', path: '/search/wholesale'}
  ]

  function openCart() {
    showMenu = false;
    dispatch('openCart', true);
  }

  let isExpanded = false;
  function clickHandler(){
    isExpanded = !isExpanded;
  }
</script>

<div  class="bg-[#224b59] w-full flex py-2 px-12">
  <div class="uppercase ml-auto text-white text-small">
    free shipping on orders of $75+ | 

  </div>

</div>

<nav class="flex justify-between border-b border-zinc-700 p-4 lg:px-6 bg-white">
    <div class="mr-4" class:active={currentRoute === '/'}>
      <a href="/" data-sveltekit-prefetch class="">
        <picture>
          <source srcset="/logo.png" type="image/png" />
          <img
            alt="Bright Endeavors Logo"
            class=" w-64"
            decoding="async"
            height={38}
            loading="eager"
            src="/logo.png"
            width={32}
          />
        </picture>
      </a>
    </div>
    <div class="hidden lg:flex items-center space-x-4">
      {#each tabs as tab}
        {#if tab.name == "shop"}
            <nav>
                <button class="text-[#224b59] opacity-80 text-xl" on:click={clickHandler}>SHOP</button>
                {#if isExpanded}
                    <div class="bg-white overflow-auto absolute py-4 z-10 text-sm">
                        <ul class="text-[#224b59] opacity-60 font-serif tracking-wider" transition:slide>
                            <li class="bg-black opacity-50 h-[0.99px] mb-2"></li>
                            {#each sublinks as sub}
                            <li class="px-6 py-2"><a href="www.google.com">{sub.name}</a></li>
                            {/each}
                        </ul>
                    </div>
                {/if}
            </nav> 
        {:else}
        <div class:active={currentRoute === tab.path}>
            <a
            data-sveltekit-prefetch
            href={tab.path}
            class={`uppercase text-xl hover:text-[#991f36] px-2 py-1 text-[#224b59] transition-colors rounded-lg ${
            currentRoute === tab.path ? 'opacity-100' : 'opacity-75'
            }`}>{tab.name}</a>
        </div>
        {/if}
      {/each}
      <div class="ml-auto flex items-center">
        <button on:click={openCart} class="relative my-2 mx-4">
          <Icons strokeColor="#244b59" type="cart" />
          <div
            data-test="cart-quantity"
            class="absolute bottom-0 left-0 -ml-3 -mb-3 flex h-5 w-5 items-center justify-center rounded-full border border-black bg-white text-xs text-black"
          >
            {$cartQuantity}
          </div>
        </button>
  </div>
  
  
    <button
      on:click={() => {
        showMenu = true;
      }}
      aria-label="Open menu"
      class="lg:hidden"
    >
      <Icons type="menu" />
    </button>
  </div>
  {#if showMenu}
    <div
      on:click|self={() => {
        showMenu = false;
      }}
      class="absolute inset-0 z-50 flex max-h-screen w-full justify-end overflow-hidden  lg:hidden"
    >
      <div class="z-30 w-full p-6 md:w-1/2 lg:w-1/3">
        <div class="flex w-full items-center justify-between">
          <button
            aria-label="Close menu"
            on:click={() => {
              showMenu = false;
            }}
          >
            <Icons strokeColor="#fff" type="close" />
          </button>
          <button on:click={openCart} class="relative mr-4">
            <Icons strokeColor="#fff" type="cart" />
            <div
              class="absolute bottom-0 left-0 -ml-3 -mb-3 flex h-5 w-5 items-center justify-center rounded-full border border-black bg-white text-xs text-black"
            >
              {$cartQuantity}
            </div>
          </button>
        </div>
        <div class="mt-6 flex w-full flex-col">
          {#each tabs as tab, i (tab.name)}
            <div
              class:active={currentRoute === tab.path}
              on:click={() => {
                showMenu = false;
              }}
            >
              <a
                data-sveltekit-prefetch
                href={tab.path}
                class={`hover:opacity-100 px-2 py-1 text-black font-bold text-xl rounded-lg ${
                  currentRoute === tab.path ? 'opacity-100' : 'opacity-75'
                }`}>{tab.name}</a
              >
            </div>
          {/each}
        </div>
      </div>
    </div>
  {/if}
</nav>
