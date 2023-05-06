<script>
    import { page } from '$app/stores';
    import { slide } from 'svelte/transition';
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();

    $: currentRoute = $page.url.pathname;

    let isExpanded_button = false;
    function clickHandler_big(){
        isExpanded_button = !isExpanded_button;
    }

    let isExpanded = false;
    function clickHandler(){
        isExpanded = !isExpanded;
    }

    let rotated = false;
    function shop_arrow(){
        rotated = !rotated;
    }

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
</script>


<div class="text-right justify-end float-right h-fit bg-white">
    <button on:click={clickHandler_big}>
        <div class="mx-4 mt-4 mb-10 py-px px-2 border-solid border-2 border-gray-300 rounded-md">
            <svg class="w-8 stroke-3 stroke-[#224b59] opacity-60" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 50 50" id="hamburger-menu"><path fill="#231F20" d="M8.667 15h30a1 1 0 100-2h-30a1 1 0 100 2zM8.667 37h30a1 1 0 100-2h-30a1 1 0 100 2zM8.667 26h30a1 1 0 100-2h-30a1 1 0 100 2z"></path></svg>
        </div>
    </button>
    {#if isExpanded_button}
        {#each tabs as tab}
            {#if tab.name == "shop"}
                <nav transition:slide class="mr-6 mb-10">
                    <button class="text-[#224b59] opacity-80 text-lg" on:click={clickHandler} on:click={shop_arrow}>SHOP 
                    {#if rotated}
                        <svg class="ml-2 mt-2 float-right rotate-90" xmlns="http://www.w3.org/2000/svg" width="10px" height="10px" viewBox="0 0 512 512" id="down-arrow"><path d="M98.9 184.7l1.8 2.1 136 156.5c4.6 5.3 11.5 8.6 19.2 8.6 7.7 0 14.6-3.4 19.2-8.6L411 187.1l2.3-2.6c1.7-2.5 2.7-5.5 2.7-8.7 0-8.7-7.4-15.8-16.6-15.8H112.6c-9.2 0-16.6 7.1-16.6 15.8 0 3.3 1.1 6.4 2.9 8.9z"></path></svg>
                    {:else}
                        <svg class="ml-2 mt-2 float-right rotate-0" xmlns="http://www.w3.org/2000/svg" width="10px" height="10px" viewBox="0 0 512 512" id="down-arrow"><path d="M98.9 184.7l1.8 2.1 136 156.5c4.6 5.3 11.5 8.6 19.2 8.6 7.7 0 14.6-3.4 19.2-8.6L411 187.1l2.3-2.6c1.7-2.5 2.7-5.5 2.7-8.7 0-8.7-7.4-15.8-16.6-15.8H112.6c-9.2 0-16.6 7.1-16.6 15.8 0 3.3 1.1 6.4 2.9 8.9z"></path></svg>
                    {/if}
                    </button>
                    {#if isExpanded}
                        <div class="bg-white py-4 z-10 text-sm text-right">
                            <ul class="text-[#224b59] opacity-60 font-serif tracking-wider" transition:slide>
                                {#each sublinks as sub}
                                <li class="py-2 hover:text-[#991f36]"><a href="/{tab.path}">{sub.name}</a></li>
                                {/each}
                                <li class="bg-black opacity-50 h-[0.99px] mb-2"></li>
                            </ul>
                        </div>
                    {/if}
                </nav> 
            {:else}
                <div class:active={currentRoute === tab.path} transition:slide class="mr-4 mb-10">
                    <a
                    data-sveltekit-prefetch
                    href={tab.path}
                    class={`uppercase text-lg hover:text-[#991f36] px-2 py-1 text-[#224b59] transition-colors rounded-lg ${
                    currentRoute === tab.path ? 'opacity-100' : 'opacity-75'
                    }`}>{tab.name}</a>
                </div>
            {/if}
        {/each}
    {/if}
</div>