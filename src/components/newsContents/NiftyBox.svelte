<script>
    let activeTab = 'Stock in News';
  const tabs = ['Stock in News', 'Stock Last Visited', 'Watchlist', 'Portfolio'];

  const newsItems = [
    {
      title: 'TATA Cons. Prod',
      description: 'Company to consider rights issue worth Rs 3,000 crore on July 23',
      stock: {
        name: 'TATA Cons. Prod',
        price: '1188.00',
        change: '-5.40 (-0.45%)',
        volume: '1.39m',
        color: 'red-600'
      }
    },
    {
      title: 'CIEINDIA',
      description: 'Q1 net profit down 28.1% at Rs 216.8 crore Vs Rs 301.7 crore, YoY',
      stock: {
        name: 'CIEINDIA',
        price: '587.85',
        change: '-18.80 (-3.1%)',
        volume: '623.02k',
        color: 'red-600'
      }
    },
    {
      title: 'Ceat',
      description: 'Q1 net profit up 6.6% at Rs 154.2 crore Vs Rs 144.6 crore, YoY',
      stock: {
        name: 'Ceat',
        price: '2675.90',
        change: '-108.50 (-3.9%)',
        volume: '443.77k',
        color: 'red-600'
      }
    },
    {
      title: 'Dr Reddys Labs',
      description: 'Signs non-exclusive patent licensing agreement with Takeda to commercialise Vonoprazan in India',
      stock: {
        name: 'Dr Reddys Labs',
        price: '6636.00',
        change: '-31.50 (-0.47%)',
        volume: '180.07k',
        color: 'red-600'
      }
    },
    {
      title: 'Infosys',
      description: 'Q1 net profit down 20% at Rs 6,368 crore Vs Rs 7,969 crore, QoQ',
      stock: {
        name: 'Infosys',
        price: '1792.95',
        change: '+34.90 (1.99%)',
        volume: '29.82m',
        color: 'green-600'
      }
    }
  ];
    let isDropdownOpen = false;
  
    function toggleDropdown() {
      isDropdownOpen = !isDropdownOpen;
    }
  </script>
  <div class="relative flex items-center w-auto border border-gray-600 p-0.5 text-[10px]">
    <div class="flex items-center justify-center space-x-4 flex-1 first-components">
      <div>SENSEX <span>80604.65</span> <span class="text-red-600">▼-738.81(-0.91%)</span></div>
      <div>NIFTY 50 <span>24530.90</span> <span class="text-red-600">▼-269.95 (-1.09%)</span></div>
      <div>NIFTY BANK <span>52265.60</span> <span class="text-red-600">▼-355.1(-0.67%)</span></div>
      <div>NIFTY Midcap 100 <span>55908.30</span> <span class="text-red-600">▼-120.8 (-2.11%)</span></div>
    </div>
    <div class="flex items-center space-x-4 second-components">
      <div class="flex space-x-1">
        <span class="w-3 h-3 bg-blue-500 rounded-full"></span>
        <span class="w-3 h-3 bg-gray-300 rounded-full"></span>
        <span class="w-3 h-3 bg-gray-300 rounded-full"></span>
        <span class="w-3 h-3 bg-gray-300 rounded-full"></span>
        <span class="w-3 h-3 bg-gray-300 rounded-full"></span>
      </div>
      <button class="focus:outline-none">
        <i class="fa-solid fa-gear"></i>
      </button>
    </div>
    <div class="absolute bottom-0 left-1/2 transform -translate-x-1/2 translate-y-1/2">
      <button class="focus:outline-none" on:click={toggleDropdown}>
        <svg class="w-6 h-6 text-black" fill="currentColor" viewBox="0 0 20 20">
          <path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
        </svg>
      </button>
    </div>
    {#if isDropdownOpen}
    <div class="flex absolute bottom-0 left-1/2 transform -translate-x-1/2 translate-y-full mt-0.5 w-auto bg-white border rounded-md shadow-lg z-10">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8 mt-1">
            <div class="border-b border-gray-200 mb-1">
              <nav class="flex space-x-2" aria-label="Tabs">
                {#each tabs as tab}
                  <a
                    href="#"
                    class="py-4 px-1 border-b-2 font-medium text-sm {tab === activeTab ? 'border-indigo-500 text-indigo-600' : 'border-transparent text-gray-500 hover:text-gray-700 hover:border-gray-300'}"
                    on:click={() => activeTab = tab}
                  >
                    {tab}
                  </a>
                {/each}
              </nav>
            </div>
          
            <div class="bg-white shadow overflow-hidden sm:rounded-md">
              <ul class="divide-y divide-gray-200">
                {#each newsItems as item}
                  <li>
                    <a href="#" class="block hover:bg-gray-50">
                      <div class="flex items-center px-4 py-1 sm:px-6">
                        <div class="flex-1 min-w-0">
                          <div class="flex items-center justify-between">
                            <p class="text-sm font-medium text-indigo-600 truncate">{item.title}</p>
                            <div class="ml-2 flex-shrink-0 flex">
                              <p class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-green-100 text-green-800">
                                {item.stock.price}
                              </p>
                            </div>
                          </div>
                          <div class="mt-1 sm:flex sm:justify-between">
                            <div class="sm:flex">
                              <p class="flex items-center text-sm text-gray-500">
                                {item.description}
                              </p>
                            </div>
                            <div class="mt-1 flex items-center text-sm text-gray-500 sm:mt-0">
                              <span class="text-{item.stock.color}">{item.stock.change}</span>
                              <span class="ml-4">{item.stock.volume}</span>
                            </div>
                          </div>
                        </div>
                      </div>
                    </a>
                  </li>
                {/each}
              </ul>
            </div>
          </div>
    </div>
    {/if}
  </div>
 