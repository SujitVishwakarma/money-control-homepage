<script>
  import { onMount } from 'svelte';

  // Dummy data
  let funds = [
    {
      name: '360 ONE Quant Fund - Direct Plan - Growth',
      threeYearReturn: 'NA',
      fiveYearReturn: 'NA'
    },
    // Add more dummy data as needed
    {
      name: 'Another Fund - Direct Plan - Growth',
      threeYearReturn: '5%',
      fiveYearReturn: '10%'
    },
    {
      name: 'Sample Fund - Direct Plan - Growth',
      threeYearReturn: '7%',
      fiveYearReturn: '12%'
    },
    {
      name: 'HSBC Value Fund - Direct Plan - Growth',
      threeYearReturn: '2%',
      fiveYearReturn: '10%'
    },
    {
      name: 'Canara Robeco Manufacturing Fund - Direct Plan (DG)',
      threeYearReturn: '12%',
      fiveYearReturn: '18%'
    },
  ];

  let currentIndex = 0;

  // Auto-slide functionality
  onMount(() => {
    const interval = setInterval(() => {
      currentIndex = (currentIndex + 1) % funds.length;
    }, 3000); // Change slide every 3 seconds

    return () => {
      clearInterval(interval);
    };
  });
</script>

<style>
  .container {
    width: auto;
  }
  .slider-wrapper {
    overflow: hidden;
    width: 100%;
    height: 100%;
  }
  .slider-container {
    display: flex;
    transition: transform 0.5s ease-in-out;
  }
  .slider-item {
    min-width: 100%;
    height: 2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0.5rem 0;
    box-sizing: border-box;
  }
  .vertical-line {
    border-left: 2px solid rgb(104, 78, 114);
    height: 1.5rem;
  }
  .equity {
    background: blue;
    color: aliceblue;
    border-radius: 8px 5px 25px 6px;
    padding-left: 4px;
  }
  .return-value {
    color: green;
  }
  @media (max-width: 768px) {
    .equity {
      font-size: 10px;
    }
    .text-xs {
      font-size: 10px;
    }
  }
</style>

<div class="container mx-auto mt-1 px-0 overflow-y-hidden border border-gray-500" style="height: 2rem;">
  <div class="slider-wrapper">
    <div class="slider-container w-full" style="transform: translateX(-{currentIndex * 100}%);">
      {#each funds as fund}
        <div class="slider-item border bg-white">
          <div class="flex items-center">
            <span class="font-bold pr-8 equity ml-2">EQUITY FUNDS</span>
            <span class="ml-8 text-xs">{fund.name}</span>
            <div class="vertical-line mx-2"></div>
          </div>
          <div class="flex items-center">
            <span class="pr-4 text-xs flex">
              3 Year Return: <span class="return-value ml-2">{fund.threeYearReturn}</span>
            </span>
            <div class="vertical-line mx-2"></div>
            <span class="pr-4 text-xs">
              5 Year Return: <span class="return-value ml-2">{fund.fiveYearReturn}</span>
            </span>
            <div class="vertical-line mx-2"></div>
            <button class="bg-orange-500 text-white px-2 py-1 rounded ml-4 text-xs">INVEST NOW</button>
            <span class="partner ml-2 mr-2 text-[10px] text-blue-500 top-0 left-0">PARTNERED BY</span>
          </div>
        </div>
      {/each}
    </div>
  </div>
</div>
