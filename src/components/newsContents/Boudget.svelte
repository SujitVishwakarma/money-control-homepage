<script>
    const image1 = new URL('../assets/budget.jpg', import.meta.url).href;
    let articles = [
      {
        title: 'Budget 2024: Travel & tourism sector seeks infra status, tweaks to LTA rules for tax exemption',
        image: 'path/to/image.jpg'
      },
      {
        title: 'Budget 2024 should increase capex outlay to Rs 13 lakh crore: Vinayak Chatterjee'
      },
      {
        title: 'Budget 2024: Faster fiscal consolidation possible while increasing welfare spending, says ICRA\'s Aditi Nayar'
      },
      {
        title: 'MC Exclusive: Centre may revive PLI scheme for manufacture of shipping containers in budget ‘24'
      },
      {
        title: 'Budget 2024: Increased welfare schemes, social spends to boost rural demand for FMCG cos'
      }
    ];
  
     let stocks = [
    { company: 'Infosys', price: 1792.95, change: 34.90, gain: 1.99 },
    { company: 'ITC', price: 474.55, change: 4.30, gain: 0.91 },
    { company: 'Asian Paints', price: 2946.05, change: 14.50, gain: 0.49 },
    { company: 'Britannia', price: 5877.95, change: 6.45, gain: 0.11 },
    { company: 'LTIMindtree', price: 5762.75, change: 5.85, gain: 0.10 }
  ];
  
    let tags = ['Budget 2024 Date', 'Budget 2024', 'LTCG Tax', 'Credit Card spend limit'];
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
    <div class="flex-1">
      <div class="border p-4">
        <h2 class="text-xl font-bold mb-4">BUDGET 2024</h2>
        <div class="flex">
          <img src="/budgetNew.jpg" alt="Main Article" class="w-1/3 mr-4" />
          <div>
            <h3 class="font-bold">{articles[0].title}</h3>
          </div>
        </div>
        <ul class="mt-4">
          {#each articles.slice(1) as article}
            <li class="border-b py-2">
              {article.title}
            </li>
          {/each}
        </ul>
      </div>
  
      <div class="border p-4 mt-4">
        <div class="flex flex-wrap gap-2">
          {#each tags as tag}
            <button class="border px-4 py-2 rounded-full bg-blue-300">{tag}</button>
          {/each}
        </div>
      </div>
    </div>
  
    <div class="flex-none w-full md:w-1/3 lg:w-1/4">
      <div class="border pr-0.5">
        <h2 class="text-xl font-bold mb-4">Top Losers</h2>
        <div class="overflow-x-auto">
          <table class="table">
            <!-- head -->
            <thead class="bg-gray-100">
              <tr>
                <th class="py-2 px-1 text-left">Company</th>
                <th class="py-2 px-1 text-right">Price</th>
                <th class="py-2 px-1 text-right">Change</th>
                <th class="py-2 px-1 text-right">%Gain</th>
              </tr>
            </thead>
            <tbody>
              {#each stocks as stock}
                <tr class="border-b">
                  <td class="py-2 px-1">{stock.company}</td>
                  <td class="py-2 px-1 text-right">{stock.price}</td>
                  <td class="py-2 px-1 text-right text-green-500">{stock.change}</td>
                  <td class="py-2 px-1 text-right text-green-500">{stock.gain}</td>
                </tr>
              {/each}
            </tbody>
          </table>
        </div>
        <button class="mt-4 border rounded-lg border-slate-400 p-1.5 text-blue-500 hover:bg-orange-500 hover:text-white ">See all Top Losers +</button>
      </div>
    </div>
  </div>
  