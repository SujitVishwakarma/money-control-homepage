<script>
  let currentCategory = 'Issues Open';

  const categories = ['Issues Open', 'Upcoming Issues', 'Listed IPOs', 'NFO', 'Recent Issues'];

  const ipoData = {
    'Issues Open': [
      { equity: 'Sanstar L', type: 'IPO', issuePrice: 90, issueSize: 150, lotSize: 150, issueOpen: '19-07', issueClose: '23-07' },
      { equity: 'Tunwal E-Motors', type: 'SME IPO', issuePrice: 59, issueSize: 115.64, lotSize: 2000, issueOpen: '15-07', issueClose: '18-07' },
      { equity: 'Kataria Industr', type: 'SME IPO', issuePrice: 91, issueSize: '51.73 - 54.58', lotSize: 1200, issueOpen: '16-07', issueClose: '19-07' },
      { equity: 'Macobs Technolo', type: 'SME IPO', issuePrice: 71, issueSize: '18.43 - 19.46', lotSize: 1600, issueOpen: '16-07', issueClose: '19-07' }
    ],
    'Upcoming Issues': [
      { equity: 'Dummy 1', type: 'IPo', issuePrice: 102, issueSize: 150, lotSize: 150, issueOpen: '19-07', issueClose: '23-07' },
      { equity: 'Dummy 2', type: 'NSe', issuePrice: 62, issueSize: 115.64, lotSize: 2000, issueOpen: '15-07', issueClose: '18-07' },
      { equity: 'Kdummy 3', type: 'Mse', issuePrice: 91, issueSize: '51.73 - 54.58', lotSize: 1200, issueOpen: '16-07', issueClose: '19-07' },
      { equity: 'Dummy 4', type: 'Tse', issuePrice: 71, issueSize: '18.43 - 19.46', lotSize: 1600, issueOpen: '16-07', issueClose: '19-07' }
    ],
    'Listed IPOs': [],
    'NFO': [
      { equity: 'Dummy 1', type: 'IPo', issuePrice: 102, issueSize: 150, lotSize: 150, issueOpen: '19-07', issueClose: '23-07' },
      { equity: 'NFO 2', type: 'NSe', issuePrice: 62, issueSize: 115.64, lotSize: 2000, issueOpen: '15-07', issueClose: '18-07' },
      { equity: 'NFO DATA 3', type: 'Mse', issuePrice: 91, issueSize: '51.73 - 54.58', lotSize: 1200, issueOpen: '16-07', issueClose: '19-07' },
      { equity: 'Dummy 4', type: 'Tse', issuePrice: 71, issueSize: '18.43 - 19.46', lotSize: 1600, issueOpen: '16-07', issueClose: '19-07' }],
    'Recent Issues': []
  };

  function changeCategory(category) {
    currentCategory = category;
  }
</script>

<style>
  .tab-active {
    border-bottom: 2px solid black;
  }
</style>

<div class="container mx-auto mt-8 px-4 sm:px-6 lg:px-8 overflow-y-hidden">
  <h1 class="text-2xl font-bold mb-2">IPO SNAPSHOT</h1>
  <div class="flex space-x-4 border-b mb-4">
    {#each categories as category}
      <button
        class="py-2 px-4 {currentCategory === category ? 'tab-active' : ''}"
        on:click={() => changeCategory(category)}
      >
        {category}
      </button>
    {/each}
  </div>

  <div>
    <table class="w-full text-left">
      <thead>
        <tr class="border-b">
          <th class="py-2">Equity</th>
          <th class="py-2">Type</th>
          <th class="py-2">Issue Price</th>
          <th class="py-2">Issue Size</th>
          <th class="py-2">Lot Size</th>
          <th class="py-2">Issue Open</th>
          <th class="py-2">Issue Close</th>
        </tr>
      </thead>
      <tbody>
        {#each ipoData[currentCategory] as ipo}
          <tr class="border-b">
            <td class="py-2">{ipo.equity}</td>
            <td class="py-2">{ipo.type}</td>
            <td class="py-2">{ipo.issuePrice}</td>
            <td class="py-2">{ipo.issueSize}</td>
            <td class="py-2">{ipo.lotSize}</td>
            <td class="py-2">{ipo.issueOpen}</td>
            <td class="py-2">{ipo.issueClose}</td>
          </tr>
        {/each}
      </tbody>
    </table>
  </div>
  <div class="bg-gray-500 w-full h-1 mt-5"></div>
</div>
