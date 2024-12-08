<script>
  import { faHome, faInfoCircle, faCrown, faBuilding, faTrophy, faEnvelope, faClipboard, faVideo, faComment, faCog, faBook, faCoffee, faGlobe, faBusinessTime, faLaptop, faFilm, faRunning, faBaseballBall, faFlask, faHeartbeat, faTimes } from "@fortawesome/free-solid-svg-icons";
  import { FontAwesomeIcon } from "@fortawesome/svelte-fontawesome";
  
  let selectedCategory = null;
  let selectedItem = null;

  function setCategory(category) {
    selectedCategory = category;
    selectedItem = null;
    showSecondSection = true;
    showThirdSection = false;
  }

  function setItem(item) {
    selectedItem = item;
    showThirdSection = true;
  }

  function handleClick() {
    alert("Signin function is Clicked");
  }

  function resetSections() {
    selectedCategory = null;
    selectedItem = null;
    showSecondSection = false;
    showThirdSection = false;
  }

  function closeSecondSection() {
    selectedCategory = null;
    selectedItem = null;
    showSecondSection = false;
    showThirdSection = false;
  }

  const categories = [
    { name: "Home", icon: faHome },
    { name: "About Us", icon: faInfoCircle },
    { name: "Internship", icon: faBuilding },
    { name: "Companies", icon: faTrophy },
    { name: "Contact Us", icon: faEnvelope },
    { name: "Case", icon: faClipboard },
    { name: "Videos", icon: faVideo },
    { name: "Message", icon: faComment },
    { name: "Preferences", icon: faCog },
    { name: "Courses", icon: faBook },
    { name: "Coworking-space", icon: faCoffee },
    { name: "INDIA", icon: faGlobe },
    { name: "World", icon: faGlobe },
    { name: "Business", icon: faBusinessTime },
    { name: "Technology", icon: faLaptop },
    { name: "Showbuzz", icon: faFilm },
    { name: "Sports", icon: faRunning },
    { name: "IPL 2024", icon: faBaseballBall },
    { name: "Science", icon: faFlask },
    { name: "Health", icon: faHeartbeat }
  ];

  const items = {
    "Home": ["Eye on Earnings", "Web Stories", "MF Simplified", "Real State", "Bonds", "IPO","MC Learn","#Bonds", "#StartupConclave","#IFBA2024"],
    "About Us": ["Item A", "Item B", "Item C", "Item D", "Item E"],
    "Internship": ["Item X", "Item Y", "Item Z", "Item W", "Item Q"],
    // Add items for other categories similarly...
  };

  const subItems = {
    "Eye on Earnings": ["SubItem 1.1", "SubItem 1.2", "SubItem 1.3", "SubItem 1.4", "SubItem 1.5"],
    "Web Stories": ["SubItem 2.1", "SubItem 2.2", "SubItem 2.3", "SubItem 2.4", "SubItem 2.5"],
    // Add sub-items for other items similarly...
  };

  // State variables to control section visibility
  let showSecondSection = false;
  let showThirdSection = false;
</script>

<style>
  .theme-controller {
    margin-right: 0.5rem;
  }
  a {
    width: 100%;
    display: flex;
    align-items: center;
  }
  .main-container {
    display: flex;
    flex-wrap: nowrap;
    height: 100vh;
  }
  .section {
    flex: 1;
    padding: 0.5rem;
    overflow-y: auto;
  }
  .sidebar {
    flex: 0 0 20%;
    min-width: 200px;
  }
  @media (max-width:320px){
    .sidebar{
      margin-top: 2rem;
    }
  }
</style>

<div class="main-container">
  <!-- Sidebar Section -->
  <div class="sidebar">
    <div class="flex flex-col h-full p-2 bg-gray-200 shadow-xm overflow-y-auto mt-8">
      <div class="flex justify-between mb-1">
        <button on:click={handleClick} class="bg-red-600 text-white py-1 px-4 rounded-full">Sign In</button>
        <button class="bg-gray-400 text-white py-2 px-4 rounded-full" on:click={resetSections}>Theme</button>
      </div>
      <button class="bg-red-600 text-white py-2 px-4 rounded-full flex items-center mb-2">
        <FontAwesomeIcon icon={faCrown} class="w-4 h-4 mr-2" /> Subscribe
      </button>
      {#each categories as { name, icon }}
        <a href="#" class="flex items-center hover:bg-gray-100 p-1 rounded-xm" on:click={() => setCategory(name)}>
          <div class="flex items-center justify-center w-12">
            <div class="w-8 h-4 flex items-center justify-center rounded-full">
              <FontAwesomeIcon icon={icon} class="w-4 h-4" />
            </div>
          </div>
          <span class="text-black">{name}</span>
        </a>
      {/each}
    </div>
  </div>

  <!-- Second Section -->
  {#if showSecondSection}
  <div class="section">
    <div class="flex justify-between items-center mb-2">
      <h2 class="text-xl font-bold">{selectedCategory}</h2>
      <button on:click={closeSecondSection} class="text-gray-500 hover:text-gray-700">
        <FontAwesomeIcon icon={faTimes} class="w-6 h-6" />
      </button>
    </div>
    <ul>
      {#each items[selectedCategory] as item}
        <li>
          <button class="hover:bg-gray-200 p-2 w-full text-left" on:click={() => setItem(item)}>{item}</button>
        </li>
      {/each}
    </ul>
  </div>
  {/if}

  <!-- Third Section -->
  {#if showThirdSection}
  <div class="section">
    {#if selectedItem}
      <h2 class="text-xl font-bold mb-2">{selectedItem}</h2>
      <ul>
        {#each subItems[selectedItem] as subItem}
          <li>{subItem}</li>
        {/each}
      </ul>
    {/if}
  </div>
  {/if}
</div>
