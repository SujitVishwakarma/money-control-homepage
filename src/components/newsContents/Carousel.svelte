<script>
  import { onMount } from "svelte";

  let news = [];
  let articles = [];
  const category = "technology"; 

  async function fetchNews() {
    try {
      const response = await fetch(
        `https://newsapi.org/v2/top-headlines?country=in&category=${category}&apiKey=enter-your-api-key`
      );
      const data = await response.json();
      news = data.articles;
      articles = data.articles.slice(4, 7);
    } catch (error) {
      console.error("Error fetching news:", error);
      news = [];
    }
  }

  onMount(fetchNews);

  function scrollCarousel(direction) {
    const carousel = document.querySelector(".carousel");
    const scrollAmount = carousel.clientWidth;
    carousel.scrollBy({ left: direction * scrollAmount, behavior: "smooth" });
  }
</script>

<div class="relative overflow-y-hidden">
  <!-- //carousel-item inserted from daisyui  -->
  <div class="carousel flex overflow-x-auto space-x-4 snap-x snap-mandatory">
    {#each news.slice(0, 10) as item, index}
      <div class="carousel-item flex-shrink-0 w-64 md:w-80 snap-center">
        <div class="card bg-white shadow-md rounded-lg overflow-hidden">
          <img
            src={item.urlToImage || "https://via.placeholder.com/400x200"}
            class="w-full h-40 object-cover"
            alt={item.title}
          />
          <div class="p-4">
            <h2 class="text-lg font-semibold">{item.title}</h2>
          </div>
        </div>
      </div>
    {/each}
  </div>
  <div class="absolute top-1/2 transform -translate-y-1/2 left-4">
    <button class="btn btn-circle" on:click={() => scrollCarousel(-1)}>❮</button
    >
  </div>  
  <div class="absolute top-1/2 transform -translate-y-1/2 right-4">
    <button class="btn btn-circle" on:click={() => scrollCarousel(1)}>❯</button>
  </div>
</div>

<!-- <p>hello is next</p> -->
<style>
  .carousel {
    scroll-snap-type: x mandatory;
    -webkit-overflow-scrolling: touch;
  }

  .carousel-item {
    scroll-snap-align: center;
  }

  .btn-circle {
    background: white;
    border: 1px solid #ddd;
    border-radius: 50%;
    width: 40px;
    height: 40px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
  }
  
</style>
