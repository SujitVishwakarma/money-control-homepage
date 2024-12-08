<script>
    let communityViews = [
      {
        time: 'ABOUT 17 SEC',
        title: 'Oil India : For clarity purpose<br />nthose who have brought shares on july 02 ar...',
        author: 'Jain_Naresh'
      },
      {
        time: 'ABOUT 19 SEC',
        title: 'Sangam Advisors : Waaree renewable secured project of 30 mw from kirlosker group in maha...',
        author: 'Investor_ns'
      },
      {
        time: 'ABOUT 48 SEC',
        title: 'NHPC : Why did it fall today any news',
        author: 'Unity2020'
      }
    ];
  
    let opinionQuestion = "Will India be a USD 5 trillion economy by FY27?";
  </script>
  
  <style>
    .community-views {
      display: flex;
      flex-direction: column;
    }
    .opinion {
      display: flex;
      flex-direction: column;
      justify-content: space-center;
      width: 50%;
      margin-left: 70px;
    }
    .subscription {
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
    .pagination {
      display: flex;
      justify-content: center;
      gap: 0.5rem;
    }
  </style>
  
  <div class="container mx-auto p-4 grid gap-4 sm:grid-cols-1 md:grid-cols-2 lg:grid-cols-3">
    <!-- Community Views Section -->
    <div class="border p-4 rounded-lg flex flex-col space-y-4 community-views">
      <h2 class="text-xl font-bold underline">COMMUNITY VIEWS</h2>
      {#each communityViews as view}
        <div>
          <p class="text-sm text-gray-500">{view.time}</p>
          <p class="text-base">{@html view.title}</p>
          <p class="text-sm text-gray-700">Posted By: {view.author}</p>
        </div>
      {/each}
      <button class="mt-4 border rounded-lg border-slate-400 p-1.5 text-blue-500 hover:bg-orange-500 hover:text-white ">See all Top Losers +</button>
      <div class="mt-4 flex items-center space-x-2">
        <input
          class="flex-grow border rounded p-2"
          placeholder="Post your stocks queries, tips and information on forum"
          style="width: 80%;"
        />
        <button class="bg-blue-500 text-white py-2 px-4 rounded hover:bg-orange-500" style="width: 20%;">POST</button>
      </div>
    </div>
  
    <!-- Your Opinion Section -->
    <div class="border p-4 rounded-lg flex flex-col space-y-4 opinion" style="width: 50%;">
      <h2 class="text-xl font-bold underline">YOUR OPINION</h2>
      <p>{opinionQuestion}</p>
      <div class="flex space-x-2">
        <button class="flex-1 bg-green-500 text-white py-2 hover:bg-orange-500 hover:text-white rounded">YES</button>
        <button class="flex-1 bg-red-500 text-white py-2  hover:text-black rounded">NO</button>
      </div>
    
    </div>
  
    <!-- Subscription Section -->
    <div class="border p-4 rounded-lg flex flex-col space-y-4 subscription">
      <h2 class="text-xl font-bold underline">Sign Up for Commodity Calls & Analysis by T Gnanasekar</h2>
      <p>Gold and Silver prices rose on Friday but closed mildly lower on profit-taking ahead of the weekend...</p>
      <button class="mt-4 border rounded-lg border-slate-400 p-1.5 text-blue-500 hover:bg-orange-500 hover:text-white w-auto ">Read Tashker Full Report</button>
      <div class="pagination mt-4">
        <div class="w-2 h-2 bg-gray-400 rounded-full"></div>
        <div class="w-2 h-2 bg-gray-400 rounded-full"></div>
        <div class="w-2 h-2 bg-blue-500 rounded-full"></div>
        <div class="w-2 h-2 bg-gray-400 rounded-full"></div>
      </div>
    </div>
  </div>
