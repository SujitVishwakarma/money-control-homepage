<script>
    import { onMount } from 'svelte';
  
    let category = 'general';
    let news = [];
  
    const categories = [
      { name: 'India', value: 'general' },
      { name: 'Gold Rate', value: 'business' },
      { name: 'Real Estate', value: 'realestate' },
      { name: 'Health', value: 'health' }
    ];
  
    const dummyData = {
      general: [
        {
          title: "Heritage not just history, but shared consciousness of humanity: PM Modi",
          description: "In his address at the opening ceremony of the 46th session of the World Heritage Committee (WHC) at the Bharat Mandapam in New Delhi, Modi also underlined the universality of...",
          urlToImage: "/india.jpg",
          url: "#"
        },
        {
          subTitle: "Aaditya Thackeray slams Maharashtra govt as video shows cops filling pothole",
          Subdescription: "Aaditya Thackeray has criticized the Maharashtra government after a video surfaced showing cops filling a pothole...",
        },
        {
          subTitle: "'If helpless people come...': Mamata Banerjee's offer for shelter as Bangladesh crisis spirals",
          Subdescription: "Mamata Banerjee has offered shelter to helpless people amidst the crisis in Bangladesh...",
        },
        {
          subTitle: "Govt clears consideration of private member's bill on free internet",
          Subdescription: "The government has cleared the consideration of a private member's bill that aims to provide ",
        },
        {
          subTitle: "Conversation with India on Pannun assassination plot has been respectful and effective, says US NSA",
          Subdescription: "The conversation between India and the US on the Pannun assassination plot has been respectful and effective...",
        },
        {
          subTitle: "Economic growth expected to rise by 5% next quarter",
          Subdescription: "Experts predict that the economic growth will rise by 5% in the next quarter due to various factors...",
        }
      ],
      business: [
        {
          title: "Gold snaps six-day rally; declines Rs 750 on muted demand, global cues",
          description: "In his address at the opening ceremony of the 46th session of the World Heritage Committee (WHC) at the Bharat Mandapam in New Delhi, Modi also underlined the universality of...",
          urlToImage: "/gold.jpg",
          url: "#"
        },
        {
          subTitle: "Aaditya Thackeray slams Maharashtra govt as video shows cops filling pothole",
          Subdescription: "Aaditya Thackeray has criticized the Maharashtra government after a video surfaced showing cops filling a pothole...",
        },
        {
          subTitle: "If helpless people come...: Mamata Banerjee's offer for shelter as Bangladesh crisis spirals",
          Subdescription: "According to All India Sarafa Assocation, the precious metal rates had closed at Rs 76,400 per 10 grams in the previous session.",
        },
        {
          subTitle: "Gold shines on rising Fed rate-cut outlook",
          Subdescription: "Gold prices edged higher on Thursday, trading not too far away from a record high scaled in the previous session, as rising anticipation of a U.S. interest rate cut in September boosted demand.",
        },
        {
          subTitle: "Govt clears consideration of private member's bill on free internet",
          Subdescription: "No citizen shall be liable to pay any kind of fee or charges or expenses which may prevent him or her from accessing internet facilities....",
        },
        {
          subTitle: " Gold soars to record as US rate-cut bets burnish appeal",
          Subdescription: "Experts predict that the economic growth will rise by 5% in the next quarter due to various factors...",
        }
      ],
      realestate: [
        {
          title: "Sujit not just history, but shared consciousness of humanity: PM Modi",
          description: "Do actresses find it toughest to rent a home? This tenant in Khar says so | The Tenant",
          urlToImage: "/realState.jpg",
          url: "#"
        },
        {
          subTitle: "Aaditya Thackeray slams Maharashtra govt as video shows cops filling pothole",
          Subdescription: "Aaditya Thackeray has criticized the Maharashtra government after a video surfaced showing cops filling a pothole...",
        },
        {
          subTitle: "'If helpless people come...': Mamata Banerjee's offer for shelter as Bangladesh crisis spirals",
          Subdescription: "Mamata Banerjee has offered shelter to helpless people amidst the crisis in Bangladesh...",
        },
        {
          subTitle: "Govt clears consideration of private member's bill on free internet",
          Subdescription: "The government has cleared the consideration of a private member's bill that aims to provide ",
        },
        {
          subTitle: "Conversation with India on Pannun assassination plot has been respectful and effective, says US NSA",
          Subdescription: "The conversation between India and the US on the Pannun assassination plot has been respectful and effective...",
        },
        {
          subTitle: "Economic growth expected to rise by 5% next quarter",
          Subdescription: "Experts predict that the economic growth will rise by 5% in the next quarter due to various factors...",
        }
      ],
      health: [
        {
          title: "The United Nations agency working to promote health, keep the world safe and serve the vulnerable.",
          description: "Data Is Untenable” Says ICMR DG Dr Rajiv Bahl | Numbers Includes All Death Not Covid Deaths Alone.",
          urlToImage: "/health.jpg",
          url: "#"
        },
        {
          subTitle: "Can Tirzepatide-based drugs Mounjaro and Zepbound manage type 2 diabetes?",
          Subdescription: "Mounjaro and Zepbound are medications used to manage type 2 diabetes by helping control blood sugar levels. They work by stimulating insulin production and lowering glucose production in the liver, contributing to better glycemic control.",
        },
        {
          subTitle: "'Symptoms of perioral dermatitis: Burning sensation, dryness, rashes and others",
          Subdescription: "Perioral dermatitis is a facial rash that typically appears around the mouth, causing redness, bumps, and mild peeling. Here are its symptoms, causes and treatment strategies.",
        },
        {
          subTitle: "Govt clears consideration of private member's bill on free internet",
          Subdescription: "The government has cleared the consideration of a private member's bill that aims to provide ",
        },
        {
          subTitle: "Conversation with India on Pannun assassination plot has been respectful and effective, says US NSA",
          Subdescription: "The conversation between India and the US on the Pannun assassination plot has been respectful and effective...",
        },
        {
          subTitle: "Economic growth expected to rise by 5% next quarter",
          Subdescription: "Experts predict that the economic growth will rise by 5% in the next quarter due to various factors...",
        }
      ],
      
    };
  
    function fetchNews(category) {
      news = dummyData[category] || [];
    }
  
    $: fetchNews(category);
  
    onMount(() => {
      fetchNews(category);
    });
  </script>
  
  <style>
    .active-category {
      @apply border-b-2 border-black;
    }
  </style>
  
  <div class="container mx-auto mt-2 px-4 sm:px-6 lg:px-8 overflow-y-hidden">
    <h1 class="text-2xl font-bold mb-4">NEWS NOT TO MISS</h1>
    <div class="flex border-b mb-4">
      {#each categories as cat}
        <button
          class="px-4 py-2 font-bold {category === cat.value ? 'active-category' : ''}"
          on:click={() => category = cat.value}
        >
          {cat.name}
        </button>
      {/each}
    </div>
  
    {#if news.length === 0}
      <p class="p-4">No news articles found</p>
    {:else}
      <div class="flex flex-wrap lg:flex-nowrap lg:space-x-4">
        <div class="w-full lg:w-1/2 p-4 border rounded-lg bg-gray-50">
          {#each news.slice(0, 1) as article}
            <div class="mb-6">
              <h2 class="font-bold text-lg mb-2">{article.title}</h2>
              {#if article.urlToImage}
                <img src={article.urlToImage} alt={article.title} class="w-full h-48 object-cover mb-4" />
              {/if}
              <p class="text-gray-700 mb-4">{article.description}</p>
              <a href={article.url} class="text-blue-500" target="_blank">Read more</a>
            </div>
          {/each}
        </div>
        <div class="w-full lg:w-1/2 p-4 space-y-4">
          {#each news.slice(2, 8) as article}
            <div class="border-b pb-2">
              <h3 class="font-bold">{article.subTitle}</h3>
              <p class="text-gray-700">{article.Subdescription}</p>
            </div>
          {/each}
        </div>
      </div>
    {/if}
  </div>
  