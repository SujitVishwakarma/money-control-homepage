
<script>
    export let title;
    export let description;
    export let buttonText;
    export let backgroundImage;
  </script>
  
  <div class="w-full md:w-1/3 p-4">
    <div class="max-w-sm rounded overflow-hidden shadow-lg">
      <div class="relative">
        <img class="w-full h-64 object-cover" src={backgroundImage} alt="Sunset">
        <div class="absolute inset-0 bg-black opacity-40"></div>
        <div class="absolute inset-0 flex flex-col justify-center items-center text-white px-4">
          <h2 class="text-lg font-semibold">{title}</h2>
          <p class="mt-2">{description}</p>
          <button class="mt-4 px-4 py-2 bg-white text-black font-semibold rounded">{buttonText}</button>
        </div>
      </div>
    </div>
  </div>
  