<script>
    import { onMount } from 'svelte';
  
    let commodities = [];
    let currencies = [];
    let bonds = [];
    let activeTab = 'MCX';
  
    async function fetchCommodities(type) {
      try {
        const response = await fetch(`https://financialmodelingprep.com/api/v3/quote/${type}?apikey=enter-your-key`);
        const data = await response.json();
        commodities = data;
      } catch (error) {
        console.error('Error fetching commodities:', error);
      }
    }
  
    async function fetchCurrencies() {
      try {
        const response = await fetch('https://financialmodelingprep.com/api/v3/forex?apikey=enter-your-key');
        const data = await response.json();
        currencies = data;
      } catch (error) {
        console.error('Error fetching currencies:', error);
      }
    }
  
    async function fetchBonds() {
      try {
        const response = await fetch('https://financialmodelingprep.com/api/v3/bonds?apikey=enter-your-keyF');
        const data = await response.json();
        bonds = data;
      } catch (error) {
        console.error('Error fetching bonds:', error);
      }
    }
  
    onMount(() => {
      fetchCommodities(activeTab);
      fetchCurrencies();
      fetchBonds();
    });
  </script>
  
  <main class="p-4 lg:flex lg:justify-around">
    <div class="w-full lg:w-1/3">
      <h2 class="text-xl font-bold">COMMODITIES</h2>
      <div class="flex justify-center mt-2">
        <button class="px-4 py-2" on:click={() => { activeTab = 'MCX'; fetchCommodities(activeTab); }} class:active="{activeTab === 'MCX'}">MCX</button>
        <button class="px-4 py-2 ml-2" on:click={() => { activeTab = 'NCDEX'; fetchCommodities(activeTab); }} class:active="{activeTab === 'NCDEX'}">NCDEX</button>
      </div>
      <ul class="mt-4">
        {#each commodities as commodity}
          <li class="flex justify-between py-2 border-b">
            <span>{commodity.name}</span>
            <span>{commodity.price}</span>
            <span class="{commodity.change > 0 ? 'text-green-500' : 'text-red-500'}">{commodity.change}</span>
            <span class="{commodity.change > 0 ? 'text-green-500' : 'text-red-500'}">{commodity.percentage}</span>
          </li>
        {/each}
      </ul>
      <button class="mt-4 px-4 py-2 bg-gray-200 w-full">+ See all commodity prices</button>
    </div>
  
    <div class="w-full lg:w-1/3 mt-8 lg:mt-0">
      <h2 class="text-xl font-bold">CURRENCIES</h2>
      <ul class="mt-4">
        {#each currencies as currency}
          <li class="flex justify-between py-2 border-b">
            <span>{currency.name}</span>
            <span>{currency.price}</span>
            <span class="{currency.change > 0 ? 'text-green-500' : 'text-red-500'}">{currency.change}</span>
            <span class="{currency.change > 0 ? 'text-green-500' : 'text-red-500'}">{currency.percentage}</span>
          </li>
        {/each}
      </ul>
      <button class="mt-4 px-4 py-2 bg-gray-200 w-full">+ See all Exchange Rates</button>
    </div>
  
    <div class="w-full lg:w-1/3 mt-8 lg:mt-0">
      <h2 class="text-xl font-bold">BONDS</h2>
      <ul class="mt-4">
        {#each bonds as bond}
          <li class="flex justify-between py-2 border-b">
            <span>{bond.name}</span>
            <span>{bond.price}</span>
            <span class="{bond.change > 0 ? 'text-green-500' : 'text-red-500'}">{bond.change}</span>
            <span class="{bond.change > 0 ? 'text-green-500' : 'text-red-500'}">{bond.percentage}</span>
          </li>
        {/each}
      </ul>
      <button class="mt-4 px-4 py-2 bg-gray-200 w-full">+ See all listed bonds</button>
    </div>
    <div class="bg-gray-500 w-full h-1 mt-5"></div>
  </main>
  
  <style>
    button.active {
      @apply bg-gray-300;
    }
  </style>
  
