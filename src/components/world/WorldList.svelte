<script>
    export let title;
    export let articles = [];
    export let seeMoreLink;
  </script>
  
  <div class="w-full lg:w-1/4 mb-4 lg:mb-0 px-4">
    <h2 class="font-semibold text-xl mb-4">{title}</h2>
    <div class="space-y-4">
      {#each articles as article}
        <div>
          {#if article.image}
            <img src={article.image} alt={article.title} class="w-full h-auto mb-2"/>
          {/if}
          <a href={article.link} class="text-black font-medium hover:text-gray-400">{article.title}</a>
          <p class="text-sm mt-2 hover:text-gray-400 ">{article.description}</p>
        </div>
      {/each}
    </div>
    <a href={seeMoreLink} class="block text-blue-600 mt-4 text-center py-2 border border-gray-400 hover:bg-orange-500 rounded-lg">
      + See More {title}
    </a>
  </div>
  