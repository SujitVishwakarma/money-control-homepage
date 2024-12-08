<script>
  import { onMount } from 'svelte';
  import axios from 'axios';
  import TopHeader from '../TopHeader.svelte';

  const API_KEY = '5bcf1bec6f9a4a1b8e8c31fcc1162132';
  let magazines = [];
  let articles = [];

  onMount(async () => {
    try {
      const response = await axios.get(`https://newsapi.org/v2/everything`, {
        params: {
          q: 'magazine',
          apiKey: API_KEY,
          sortBy: 'publishedAt',
          language: 'en',
        }
      });
      const sortedMagazines = response.data.articles.sort((a, b) => new Date(b.publishedAt) - new Date(a.publishedAt));
      magazines = sortedMagazines.slice(0, 8);
      articles = sortedMagazines.slice(0, 6);
    } catch (error) {
      console.error("Error fetching the magazine data", error);
    }
  });
</script>

<style>
  .container {
    margin-top: 4rem; /* Adjust based on the height of your header */
  }
</style>

<TopHeader />

<div class="container mx-auto mt-8 px-4 sm:px-6 lg:px-8 overflow-y-hidden">
  <h1 class="text-2xl font-bold mb-4 text-black">Latest Magazines</h1>
  <div class="grid gap-4 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4">
    {#if magazines.length === 0}
      <p class="p-4">No magazine articles found</p>
    {:else}
      {#each magazines as magazine, index}
        <div class="p-6 h-80 rounded-xl shadow-lg bg-white border border-gray-200 flex flex-col transition-transform transform hover:scale-105" key={index}>
          <h2 class="text-xl font-semibold mb-2 overflow-hidden text-ellipsis">{magazine.title}</h2>
          <!-- <p class="text-gray-700 mb-4 overflow-auto">{magazine.description}</p> -->
          {#if magazine.urlToImage}
            <div class="mb-4 overflow-hidden rounded-lg flex-shrink-0">
              <img src={magazine.urlToImage} alt={magazine.title} class="w-full h-32 object-cover rounded-lg">
            </div>
          {/if}
          <a href={magazine.url} target="_blank" rel="noopener noreferrer" class="text-blue-500 mt-auto">Read more</a>
        </div>
      {/each}
    {/if}
  </div>
  <h2 class="text-xl font-bold mt-6 mb-4 text-black">Latest Articles</h2>
  <div class="grid gap-4 sm:grid-cols-1 md:grid-cols-2 lg:grid-cols-3">
    {#each articles as article, index}
      <div class="p-6 h-80 rounded-xl shadow-lg bg-white border border-gray-200 flex flex-col transition-transform transform hover:scale-105" key={index}>
        <h3 class="text-lg font-semibold mb-2 overflow-hidden text-ellipsis">{article.title}</h3>
        <!-- <p class="text-gray-700 mb-4 overflow-auto">{article.description}</p> -->
        {#if article.urlToImage}
          <div class="mb-4 overflow-hidden rounded-lg flex-shrink-0">
            <img src={article.urlToImage} alt={article.title} class="w-full h-32 object-cover rounded-lg">
            </div>
        {/if}
        <a href={article.url} target="_blank" rel="noopener noreferrer" class="text-blue-500 mt-auto">Read more</a>
      </div>
    {/each}
  </div>
  <div class="bg-gray-500 w-full h-1 mt-5"></div>
</div>