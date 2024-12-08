<script>
  import { onMount } from 'svelte';
  import Carousel from './Carousel.svelte';
  import Destination from './Destination.svelte';
  import Boudget from './Boudget.svelte';
  import FundSlider from '../FundSlider.svelte';
  import NewsCard from './NewsCard.svelte';

  let category = 'general';
  let news = [];

  const categories = [
    { name: 'Top News', value: 'general' },
    { name: 'Buzzing News', value: 'entertainment' },
    { name: 'Latest News', value: 'business' },
    { name: 'Hindi', value: 'hindi' },
    { name: 'PodCast', value: 'podcast' }
  ];

  async function fetchNews(category) {
    try {
      const response = await fetch(`https://newsapi.org/v2/top-headlines?country=in&category=${category}&apiKey=xyz`);
      if (!response.ok) {
        throw new Error('Network response was not ok');
      }
      const data = await response.json();
      if (!data.articles) {
        throw new Error('No articles found in the response');
      }
      news = data.articles.slice(0, 4);
    } catch (error) {
      console.error('Error fetching news:', error);
      news = [];
    }
  }

  $: fetchNews(category);

  onMount(() => {
    fetchNews(category);
  });
</script>

<style>
  .neumorphism {
    @apply shadow-lg;
  }
  .news-container {
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    gap: 1rem;
  }
  @media (min-width: 640px) {
    .news-container {
      grid-template-columns: repeat(2, 1fr);
    }
  }
</style>

<div class="container mx-auto mt-2 px-4 sm:px-6 lg:px-8 overflow-y-hidden">
  <div class="lg:ml-10 mt-0 w-full lg:w-auto">
    <FundSlider/>
    <div class="flex justify-around p-1 h-4 pb-2">
      {#each categories as cat}
        <button
          class="px-4 py-0 font-bold {category === cat.value ? 'text-blue-500 underline' : 'text-gray-700'}"
          on:click={() => category = cat.value}
        >
          {cat.name}
        </button>
      {/each}
    </div>

    {#if news.length === 0}
      <p class="p-4">No news articles found</p>
    {:else}
      <div class="p-4 news-container">
        {#each news as article}
          <NewsCard {article} />
        {/each}
      </div>
    {/if}
    <h2 class="text-xl font-bold mt-6 mb-6 text-black">Recent Technology News</h2>
    <Carousel/>
    <Destination/>
    <Boudget/>
  </div>
</div>
