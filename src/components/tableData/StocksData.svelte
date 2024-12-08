<script>
  let commodities = {
    mcx: [
      { name: 'Gold', date: 'Aug 05', price: '74,321.00', change: '184.00', percent: '0.25%' },
      { name: 'Silver', date: 'Sep 05', price: '92,309.00', change: '367.00', percent: '0.40%' },
      { name: 'Crudeoil', date: 'Jul 19', price: '6,923.00', change: '12.00', percent: '0.17%' },
      { name: 'Naturalgas', date: 'Jul 26', price: '172.70', change: '2.20', percent: '1.29%' }
    ],
    ncdex: [
      { name: 'Wheat', date: 'Aug 10', price: '2,450.00', change: '10.00', percent: '0.41%' },
      { name: 'Soybean', date: 'Sep 20', price: '4,230.00', change: '25.00', percent: '0.59%' },
      { name: 'Corn', date: 'Jul 25', price: '1,150.00', change: '-15.00', percent: '-1.29%' },
      { name: 'Sugar', date: 'Jul 30', price: '3,200.00', change: '5.00', percent: '0.16%' }
    ]
  };

  let currencies = [
    { name: 'USDINR', date: 'Jul 29', price: '83.6525', change: '0.05', percent: '0.06%' },
    { name: 'EURINR', date: 'Jul 29', price: '91.4700', change: '0.36', percent: '0.39%' },
    { name: 'JPYINR', date: 'Jul 29', price: '53.4250', change: '0.82', percent: '1.56%' },
    { name: 'GBPINR', date: 'Jul 29', price: '108.6300', change: '0.26', percent: '0.24%' }
  ];

  let bonds = [
    { name: 'Nhpc', price: '108.30', change: '-4.91', percent: '-4.34%' },
    { name: 'Sbi', price: '893.55', change: '12.85', percent: '1.46%' },
    { name: 'Rec', price: '610.05', change: '-7.65', percent: '-1.24%' },
    { name: 'Ntpc', price: '377.75', change: '-2.70', percent: '-0.71%' }
  ];

  let currentCommodity = 'mcx';

  function setCommodity(commodity) {
    currentCommodity = commodity;
  }
</script>

<style>
  .container {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    padding: 1rem;
  }

  @media (min-width: 768px) {
    .container {
      flex-direction: row;
      justify-content: space-between;
    }
  }
</style>

<div class="container mx-auto">
  <!-- Commodities Section -->
  <div class="border p-4 flex-1">
    <div class="flex justify-between items-center mb-4">
      <h2 class="text-xl font-bold underline hover:text-orange-500">COMMODITIES</h2>
      <div class="flex">
        <button
          class={`px-2 py-1 ${currentCommodity === 'mcx' ? 'bg-blue-300 rounded hover:bg-orange-500 hover:text-white' : ''}`}
          on:click={() => setCommodity('mcx')}
        >
          MCX
        </button>
        <button
          class={`px-2 py-1 ${currentCommodity === 'ncdex' ? 'bg-blue-300 rounded hover:bg-orange-500 hover:text-white' : ''}`}
          on:click={() => setCommodity('ncdex')}
        >
          NCDEX
        </button>
      </div>
    </div>
    <table class="w-full">
      <thead>
        <tr>
          <th class="text-left">Commodity</th>
          <th class="text-right">Price</th>
          <th class="text-right">Change</th>
          <th class="text-right">% Chg</th>
        </tr>
      </thead>
      <tbody>
        {#each commodities[currentCommodity] as commodity}
          <tr>
            <td>{commodity.name} <span class="text-gray-500 text-sm">{commodity.date}</span></td>
            <td class="text-right">{commodity.price}</td>
            <td class="text-right text-green-500">{commodity.change}</td>
            <td class="text-right text-green-500">{commodity.percent}</td>
          </tr>
        {/each}
      </tbody>
    </table>
    <button class="mt-4 border rounded-lg border-slate-400 p-1.5 text-blue-500 hover:bg-orange-500 hover:text-white ">See all Top Losers +</button>
  </div>

  <!-- Currencies Section -->
  <div class="border p-4 flex-1">
    <h2 class="text-xl font-bold mb-4 underline hover:text-orange-500">CURRENCIES</h2>
    <table class="w-full">
      <thead>
        <tr>
          <th class="text-left">Currency</th>
          <th class="text-right">Price</th>
          <th class="text-right">Change</th>
          <th class="text-right">% Chg</th>
        </tr>
      </thead>
      <tbody>
        {#each currencies as currency}
          <tr>
            <td>{currency.name} <span class="text-gray-500 text-sm">{currency.date}</span></td>
            <td class="text-right">{currency.price}</td>
            <td class="text-right text-green-500">{currency.change}</td>
            <td class="text-right text-green-500">{currency.percent}</td>
          </tr>
        {/each}
      </tbody>
    </table>
    <button class="mt-4 border rounded-lg border-slate-400 p-1.5 text-blue-500 hover:bg-orange-500 hover:text-white ">See all Top Losers +</button>
  </div>

  <!-- Bonds Section -->
  <div class="border p-4 flex-1">
    <h2 class="text-xl font-bold mb-4 underline hover:text-orange-500">BONDS</h2>
    <table class="w-full">
      <thead>
        <tr>
          <th class="text-left">Name</th>
          <th class="text-right">Price</th>
          <th class="text-right">Change</th>
          <th class="text-right">% Chg</th>
        </tr>
      </thead>
      <tbody>
        {#each bonds as bond}
          <tr>
            <td>{bond.name}</td>
            <td class="text-right">{bond.price}</td>
            <td class="text-right text-red-500">{bond.change}</td>
            <td class="text-right text-red-500">{bond.percent}</td>
          </tr>
        {/each}
      </tbody>
    </table>
    <button class="mt-4 border rounded-lg border-slate-400 p-1.5 text-blue-500 hover:bg-orange-500 hover:text-white ">See all Top Losers +</button>
  </div>
</div>
