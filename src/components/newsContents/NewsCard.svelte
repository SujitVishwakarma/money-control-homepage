<!-- NewsCard.svelte -->
<script>
    export let article;
  </script>
  
  <div class="p-6 rounded-xl shadow-lg bg-white border border-gray-200 flex flex-col neumorphism">
    <h2 class="text-xl font-bold mb-2">{article.title}</h2>
    <p class="text-gray-700 mb-4">{article.description}</p>
    {#if article.urlToImage}
      <div class="mb-4 overflow-hidden rounded-lg">
        <img src={article.urlToImage} alt={article.title} class="w-full h-48 object-cover" />
      </div>
    {/if}
    <a href={article.url} target="_blank" rel="noopener noreferrer" class="text-blue-500">Read more</a>
  </div>
  
  <style>
    .neumorphism {
      @apply shadow-lg;
    }
  </style>
  