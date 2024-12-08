
<script>
    import Card from './Card.svelte';
    const image1 = new URL('../assets/world.jpg', import.meta.url).href;
    const image2 = new URL('../assets/nespaper.jpg', import.meta.url).href;
    const image3 = new URL('../assets/glory.jpg', import.meta.url).href;
  </script>
  
  <div class="flex flex-wrap justify-center">
    <div class="flex">
      <Card
      title="Destinations"
      description="Go to see the best sunsets in the world"
      buttonText="Browse Destinations"
      backgroundImage={image1}
    />
    <Card
      title="Destinations"
      description="Go to see the best sunsets in the world"
      buttonText="Browse Destinations"
      backgroundImage={image2}
    />
    <Card
      title="Destinations"
      description="Go to see the best sunsets in the world"
      buttonText="Browse Destinations"
      backgroundImage={image3}
    />
    </div>
    
    <div class="bg-gray-500 w-full h-1 mt-5"></div>
  </div>
<style>
  @media (max-width:425px){
    .cardBox{
      display: flex;
      flex-direction: column;
      justify-content: center;
      width: 120%;
    }
  }
</style>
