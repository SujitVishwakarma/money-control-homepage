<script>
    export let currencies = [];
  </script>
  
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
  