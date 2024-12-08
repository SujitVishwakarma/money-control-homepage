<script>
  import { onMount } from 'svelte';
  import {
    faUser,
    faClipboardList,
    faGift,
    faBell,
    faEnvelope,
    faDollarSign,
    faBars,
    faSearch
  } from "@fortawesome/free-solid-svg-icons";
  import { FontAwesomeIcon } from "@fortawesome/svelte-fontawesome";
  import SideBar from "./SideBar.svelte";

  export let options = ["Special", "Option 2", "Option 3"];
  export let option = ["English", "Hindi", "Gujarati"];

  let isOpen = false;
  let dropdownRef;

  function toggleDropdown() {
    isOpen = !isOpen;
  }

  function handleClickOutside(event) {
    if (dropdownRef && !dropdownRef.contains(event.target)) {
      isOpen = false;
    }
  }

  onMount(() => {
    document.addEventListener('click', handleClickOutside);
    return () => {
      document.removeEventListener('click', handleClickOutside);
    };
  });
</script>

<nav class="fixed flex items-center justify-between w-full px-2 bg-white shadow-md h-8 top-0 z-50">
  <!-- Menu bar start -->
  <div class="flex items-center space-x-1">
    <div class="drawer w-12">
      <input id="my-drawer" type="checkbox" class="drawer-toggle" />
      <div class="drawer-content p-0">
        <label for="my-drawer" class="text-black border-none hover:bg-slate-50 p-0">
          <FontAwesomeIcon icon={faBars} class="p-1" />
        </label>
      </div>
      <div class="drawer-side hover:bg-slate-50 w-full h-full">
        <label for="my-drawer" aria-label="close sidebar" class="drawer-overlay"></label>
        <ul class="menu bg-base-200 text-base-content min-h-full w-auto flex justify-between">
          <li><SideBar /></li>
        </ul>
      </div>
    </div>
    <div class="hidden md:block">
      <select class="w-full px-1 py-0.5 border rounded-md bg-gray-100 text-black focus:outline-none focus:ring-2 focus:ring-blue-500">
        {#each option as opt}
          <option>{opt}</option>
        {/each}
      </select>
    </div>
    <div class="hidden md:block">
      <select class="w-full px-1 py-0.5 text-black border rounded-md bg-gray-200 focus:outline-none focus:ring-2 focus:ring-blue-500">
        {#each options as opt}
          <option>{opt}</option>
        {/each}
      </select>
    </div>
  </div>
  <div class="relative flex-2 mx-2">
    <input
      type="text"
      placeholder="Search Quotes, News, Mutual Fund NAVs"
      class="w-full bg-white pl-2 pr-6 border border-gray-500 rounded-full focus:outline-none focus:ring-2 focus:ring-blue-500"
    />
    <div class="absolute inset-y-0 right-2 flex items-center pointer-events-none">
      <FontAwesomeIcon icon={faSearch} class="text-gray-500" />
    </div>
  </div>
  <div class="hidden md:flex items-center space-x-1">
    <div class="flex items-center bg-slate-300 justify-center px-1 text-black rounded-md hover:bg-gray-300">
      <FontAwesomeIcon icon={faBell} class="text-sm text-black" />
      <span class="ml-1 text-xs">Alerts</span>
    </div>
    <div class="flex items-center justify-center px-1 text-black bg-yellow-200 rounded-md">
      <button class="text-xs">Free Add</button>
    </div>
    <div class="relative inline-block text-left" bind:this={dropdownRef}>
      <div>
        <button
          type="button"
          class="inline-flex justify-center w-full rounded-md border border-gray-300 shadow-sm px-2 py-1 bg-white text-xs font-medium text-gray-700 hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
          on:click={toggleDropdown}
        >
          <FontAwesomeIcon icon={faUser} class="mr-1" />Hello
        </button>
      </div>

      {#if isOpen}
        <div class="dropdown-content origin-top-right absolute right-0 mt-2 w-64 rounded-md shadow-lg bg-white ring-1 ring-black ring-opacity-5 focus:outline-none z-10">
          <div class="py-1" role="menu" aria-orientation="vertical" aria-labelledby="options-menu">
            <div class="p-4 border rounded-lg shadow-lg">
              <div class="flex justify-between items-center mb-4">
                <button class="btn bg-blue-600 text-white hover:bg-orange-500 rounded-full">Log-in</button>
                <span>or</span>
                <button class="btn btn-secondary hover:bg-orange-500 rounded-full">Sign-Up</button>
              </div>
              <div class="my-4 text-black">
                <h2 class="text-xl font-semibold text-black">My Account</h2>
                <ul class="mt-2 space-y-2">
                  <li class="flex items-center cursor-pointer">
                    <FontAwesomeIcon icon={faUser} class="mr-2" /> My Profile
                  </li>
                  <li class="flex items-center cursor-pointer">
                    <FontAwesomeIcon icon={faClipboardList} class="mr-2" /> My Portfolio
                  </li>
                  <li class="flex items-center cursor-pointer">
                    <FontAwesomeIcon icon={faClipboardList} class="mr-2" /> My Watchlist
                  </li>
                  <li class="flex items-center text-green-600 cursor-pointer">
                    <FontAwesomeIcon icon={faGift} class="mr-2" /> ₹100 Cash Reward
                  </li>
                  <li class="flex items-center cursor-pointer">
                    <FontAwesomeIcon icon={faBell} class="mr-2" /> My Alerts
                  </li>
                  <li class="flex items-center cursor-pointer">
                    <FontAwesomeIcon icon={faEnvelope} class="mr-2" /> My Messages
                  </li>
                  <li class="flex items-center cursor-pointer">
                    <FontAwesomeIcon icon={faDollarSign} class="mr-2" /> Price Alerts
                  </li>
                </ul>
              </div>
              <div class="mt-4">
                <h3 class="text-lg font-semibold text-black">Follow us on:</h3>
                <div class="flex space-x-2 mt-2">
                  <a href="#" class="text-blue-600"><i class="fab fa-facebook-f"></i></a>
                  <a href="#" class="text-blue-400"><i class="fab fa-twitter"></i></a>
                  <a href="#" class="text-pink-600"><i class="fab fa-instagram"></i></a>
                  <a href="#" class="text-blue-500"><i class="fab fa-linkedin-in"></i></a>
                  <a href="#" class="text-blue-300"><i class="fab fa-telegram-plane"></i></a>
                  <a href="#" class="text-red-600"><i class="fab fa-youtube"></i></a>
                </div>
              </div>
            </div>
          </div>
        </div>
      {/if}
    </div>
  </div>
</nav>

<style>
  .drawer-content {
    padding: 0;
  }
  .drawer-button {
    min-width: 100px; 
  }
  @media (max-width: 768px) {
    .hidden {
      display: none;
    }
    .flex-1 {
      flex: 1;
      margin: 0;
    }
  }
</style>
